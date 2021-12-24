# 使用 Python 从网络摄像头中提取视频帧并保存到图像中

> 原文:[https://www . geeksforgeeks . org/extract-video-frames-从网络摄像头提取并保存到图像-使用 python/](https://www.geeksforgeeks.org/extract-video-frames-from-webcam-and-save-to-images-using-python/)

[OpenCV](https://www.geeksforgeeks.org/opencv-python-tutorial/) 库可以对视频进行多种操作。让我们尝试使用 CV2 做一些有趣的事情。乐把视频录制成网络摄像头，然后把视频一帧一帧地分解，保存下来。

## 装置

这个模块没有内置 Python。要安装它，请在终端中键入以下命令。

```py
pip install opencv-python
```

**所需步骤。**

1.  使用 **cv2 打开视频文件。视频捕捉(< path_of_video > )** 或者如果你没有任何视频，你可以使用 **cv2 直接使用你的内置摄像头。VideoCapture(0)** 命令。
2.  逐帧读取
3.  使用 cv2.imwrite()保存每个帧
4.  释放视频捕获并销毁所有窗口

下面是实现。

## 蟒蛇 3

```py
import cv2

# Opens the inbuilt camera of laptop to capture video.
cap = cv2.VideoCapture(0)
i = 0

while(cap.isOpened()):
    ret, frame = cap.read()

    # This condition prevents from infinite looping
    # incase video ends.
    if ret == False:
        break

    # Save Frame by Frame into disk using imwrite method
    cv2.imwrite('Frame'+str(i)+'.jpg', frame)
    i += 1

cap.release()
cv2.destroyAllWindows()
```

**输出:**

![python opencv extract frames from video](img/17da0caddc2af8a153ef03532fd842b1.png)