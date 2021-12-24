# 使用运行平均值的概念在图像中减去背景

> 原文:[https://www . geesforgeks . org/background-减法-在图像中使用运行平均值的概念/](https://www.geeksforgeeks.org/background-subtraction-in-an-image-using-concept-of-running-average/)

**背景减除**是一种从背景中分离出前景元素的技术，通过生成前景遮罩来完成。这种技术用于从静态摄像机中检测动态移动的物体。背景减除技术对于目标跟踪非常重要。背景减除有几种技术

在本文中，我们讨论了**运行平均值**的概念。函数的运行平均值用于将前景和背景分开。在这个概念中，在特定的一组帧上分析视频序列。在这个帧序列期间，计算当前帧和先前帧的运行平均值。这为我们提供了背景模型，在视频排序过程中引入的任何新对象都将成为前景的一部分。然后，当前帧保存新引入的带有背景的对象。然后计算背景模型(它是时间的函数)和当前帧(它是新引入的对象)之间的绝对差值。使用下面给出的公式计算运行平均值:

**先决条件:**

*   用于输入的工作网络摄像机或摄像机模块。
*   下载 Python 3.x、Numpy 和 OpenCV 2.7.x 版本。检查您的操作系统是 32 位还是 64 位兼容，并相应地安装。
*   检查 numpy 和 OpenCV 的运行状态

****Running Average 方法是如何工作的？**T3】**

该程序的目标是根据从参考帧和当前帧获得的差异来检测活动对象。我们不断地将每一帧输入给给定的函数，函数不断地寻找所有帧的平均值。然后我们计算帧之间的绝对差异。
使用的功能是 **[cv2 .累计加权()](https://docs.opencv.org/2.4/modules/imgproc/doc/motion_analysis_and_object_tracking.html?highlight=accumulate#accumulateweighted)** 。

```

cv2.accumulateWeighted(src, dst, alpha)

```

该函数中传递的参数有:

1.  **src** :源图像。图像可以是彩色或灰度图像，也可以是 8 位或 32 位浮点。
2.  **dst** :累加器或目的图像。它是 32 位或 64 位浮点。
    *注意:应该和源图像的通道一样。此外，dst 的值最初应该预先声明。*
3.  **alpha** :输入图像的权重。阿尔法决定更新的速度。如果为该变量设置一个较低的值，运行平均值将在大量先前帧上执行，反之亦然。

**代码:**

```
# Python program to illustrate
# Background subtraction using
# concept of Running Averages

# organize imports
import cv2
import numpy as np

# capture frames from a camera
cap = cv2.VideoCapture(0)

# read the frames from the camera
_, img = cap.read()

# modify the data type
# setting to 32-bit floating point
averageValue1 = np.float32(img)

# loop runs if capturing has been initialized. 
while(1):
    # reads frames from a camera 
    _, img = cap.read()

    # using the cv2.accumulateWeighted() function
    # that updates the running average
    cv2.accumulateWeighted(img, averageValue1, 0.02)

    # converting the matrix elements to absolute values 
    # and converting the result to 8-bit. 
    resultingFrames1 = cv2.convertScaleAbs(averageValue1)

    # Show two output windows
    # the input / original frames window
    cv2.imshow('InputWindow', img)

    # the window showing output of alpha value 0.02
    cv2.imshow('averageValue1', resultingFrames1)

    # Wait for Esc key to stop the program 
    k = cv2.waitKey(30) & 0xff
    if k == 27: 
        break

# Close the window 
cap.release() 

# De-allocate any associated memory usage 
cv2.destroyAllWindows()
```

**输出:**

如下图所示，手挡住了背景。
![](img/1e91cc8cbd9e62cb1bc6528e3af5cecf.png)

现在，我们摇动前景物体，即我们的手。我们开始挥手。

Running average 下面清晰的显示了背景，alpha 0.02 的 Running Average 已经捕捉到它是一只透明的手，主要强调背景
![](img/d0b19beed9984007d44bf0ac3c1a857d.png)

或者，我们可以使用 **[cv。running gavg()](https://docs.opencv.org/2.4/modules/imgproc/doc/motion_analysis_and_object_tracking.html?highlight=running#cv.RunningAvg)**用于相同的任务，其参数与 cv2.accumulateweighted()的参数具有相同的含义。

```

cv.RunningAvg(image, acc, alpha)

```

**参考文献**:

1.  https://docs.opencv.org/2.4/modules/imgproc/doc/motion_analysis_and_object_tracking.html
2.  https://en.wikipedia.org/wiki/Foreground_detection
3.  https://docs.opencv.org/3.2.0/d1/dc5/tutorial_background_subtraction.html