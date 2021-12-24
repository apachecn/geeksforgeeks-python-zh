# 使用 Python 混合两个视频

> 原文:[https://www . geeksforgeeks . org/混合两个视频-使用-python/](https://www.geeksforgeeks.org/blending-of-two-videos-using-python/)

**先决条件:** [使用 Python 中的 OpenCV 添加和混合图像](https://www.geeksforgeeks.org/addition-blending-images-using-opencv-python/)

在本文中，我们将向您展示如何有效地将两个视频混合在一起。但为此，我们将首先看到什么是阿尔法混合。

## **阿尔法混合**

Alpha 混合是两种色调的弯曲混合，考虑到了计算机插图中的透明度影响。色码中 alpha 的估计值从 0.0 到 1.0，其中 0.0 表示完全透明的色调，1.0 表示完全暗的色调。当在颜色值 0 的基础上绘制 alpha 值为 Alpha 的颜色值 1 时，后续颜色的估计值由下式给出:

```
Value = Value0(1.0 - Alpha) + Value1(Alpha)  
```

阿尔法部分可以类似地用于混合红色、绿色和蓝色片段，如在 32 位 RGBA 中，或者，同样，可以确定与用于光谱色调偏移的每个基本色调相关的三种阿尔法质量。

现在，我们将使用的第二个东西是 OpenCV，这是一个专注于实时计算机视觉的编程函数库。但是，在前进之前，我们会记下一些事情。

### 要点

为了让我们的程序完美运行，您必须确保:

1.  两个输入视频的分辨率和帧速率必须完全相同(在代码中，它使用的是 1920×1080 格式，因此只能使用这种格式，否则您必须使用输入视频的分辨率相应地设置“h”、“w”值，我们将在后面的代码中看到)
2.  编写代码时，考虑到背景视频的持续时间略大于或等于前景视频的持续时间，因此您最好也对背景和前景输入视频执行相同的操作，否则您必须将“ret”值分配给背景，而不是我们将在代码后面看到的前景
3.  用某个唯一的名称重命名您的视频文件，因为如果有两个同名的视频文件，有时可能会导致错误，并且还必须准确提供两个输入视频文件的路径。
4.  前景视频必须是一些纯色背景(最好是黑色)和主题在其上的一些运动的组合。

### **方法论**

我们将把两个视频作为输入，一个是我们的背景视频，第二个是我们的前景视频。主要工作是移除这个前景视频的纯色背景，这样我们只剩下(前景视频的)主题及其透明背景。做了这个改动之后，前景视频就会放在背景视频上，会给人一种单一视频的错觉，对它有一些影响，但实际上，会有两个视频混合在一起。这个魔术是在 OpenCV 和 Python 的帮助下完成的。

### 逐步方法

*   导入所需模块
*   添加路径并捕获两个输入视频。
*   迭代两个视频的每一帧，并使用 **Alpha 混合**将它们混合在一起。
*   播放生成的输出视频。

### 履行

**输入:**

<video class="wp-video-shortcode" id="video-557260-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210212033214/z.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210212033214/z.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210212033214/z.mp4)</video>

前景视频

<video class="wp-video-shortcode" id="video-557260-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210212033643/v.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210212033643/v.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210212033643/v.mp4)</video>

背景视频

请注意，前景视频只包含黑色背景的粒子，因此为了获得更好的效果，最好拍摄前景视频和背景视频。

## 蟒蛇 3

```
# importing necessary packages
import numpy as np
import cv2

# assigning path of foreground video
path_1 = r"C://Users//Lenovo//Desktop//Python Workshop//z.mp4"
fg = cv2.VideoCapture(path_1)

# assigning path of background video
path_2 = r"C://Users//Lenovo//Desktop//Python Workshop//v.mp4"
bg = cv2.VideoCapture(path_2)
h, w = 1080, 1920

while True:

    # Reading the the two input videos
    # we have taken "ret" here because the duration
    # of bg video is greater than fg video,
    ret, foreground = fg.read()

    # if in your case the situation is opposite
    # then take the "ret" for bg video
    _, background = bg.read()

    # if foreground array is not empty which
    # means actual video is still going on
    if ret:

        # creating the alpha mask
        alpha = np.zeros_like(foreground)
        gray = cv2.cvtColor(foreground, cv2.COLOR_BGR2GRAY)
        alpha[:, :, 0] = gray
        alpha[:, :, 1] = gray
        alpha[:, :, 2] = gray

        # converting uint8 to float type
        foreground = foreground.astype(float)
        background = background.astype(float)

        # normalizing the alpha mask inorder
        # to keep intensity between 0 and 1
        alpha = alpha.astype(float)/255

        # multiplying the foreground
        # with alpha matte
        foreground = cv2.multiply(alpha,
                                  foreground)

        # multiplying the background
        # with (1 - alpha)
        background = cv2.multiply(1.0 - alpha,
                                  background)

        # adding the masked foreground
        # and background together
        outImage = cv2.add(foreground,
                           background)

        # resizing the masked output
        ims = cv2.resize(outImage, (980, 540))

        # showing the masked output video
        cv2.imshow('Blended', ims/255)

        # if the user presses 'q' then the
        # program breaks from while loop
        if cv2.waitKey(1) & 0xFF == ord('q'):
            break
    # if the actual video is over then there's
    # nothing in the foreground array thus
    # breaking from the while loop
    else:
        break

print('Video Blending is done perfectly')
```

**输出:**

<video class="wp-video-shortcode" id="video-557260-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210212043805/yehew1.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20210212043805/yehew1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210212043805/yehew1.mp4)</video>

请注意，在这个输出视频中，我们可以看到沙子在炎热的沙漠地区的空气中移动，这实际上是粒子视频(用作前景)和沙漠视频(用作背景)的混合输出。此外，您可以随时从键盘上按“q”来中断循环并退出程序。

因此，通过这种方式，您可以混合两个视频，如果操作正确，这种方法还可以提供专业的编辑外观。