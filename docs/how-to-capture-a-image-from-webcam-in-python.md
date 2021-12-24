# 如何用 Python 从网络摄像头捕捉图像？

> 原文:[https://www . geesforgeks . org/如何从 python 网络摄像头捕获图像/](https://www.geeksforgeeks.org/how-to-capture-a-image-from-webcam-in-python/)

在本文中，我们将讨论如何使用 Python 从网络摄像头中捕获图像。

我们将使用 [OpenCV](https://www.geeksforgeeks.org/opencv-overview/) 和 [PyGame](https://www.geeksforgeeks.org/introduction-to-pygame/) 库。这两个库都包括各种捕捉图像和视频的方法和功能。通过使用这些庞大的库，我们只需要编写 4 到 5 行代码来捕获图像。

## **方法一:使用 OpenCV**

OpenCV 库兼容 Linux 和 windows 两种操作系统。用户需要使用下面的命令在本地计算机上安装 OpenCV 库，然后才能继续。

```
Install command - pip install opencv-python
```

### 方法

1.导入 OpenCV 库

2.使用 [VideoCapture()](https://www.geeksforgeeks.org/python-opencv-capture-video-from-camera/) 方法初始化相机。

**语法:**

## 蟒蛇 3

```
cam = VideoCapture(0)
```

3.使用 cam.read()方法使用相机读取输入。

**语法**:

## 蟒蛇 3

```
result, image = cam.read()
```

4.如果检测到输入图像没有任何错误，则显示输出

**语法**:

```
If result:

    # show the image
    imshow("GeeksForGeeks", image)

    # save the image
    imwrite("GeeksForGeeks.png", image)

else:
    Move to this part is input image has some error
```

#### **示例:**

## 蟒蛇 3

```
# program to capture single image from webcam in python

# importing OpenCV library
from cv2 import *

# initialize the camera
# If you have multiple camera connected with
# current device, assign a value in cam_port
# variable according to that
cam_port = 0
cam = VideoCapture(cam_port)

# reading the input using the camera
result, image = cam.read()

# If image will detected without any error,
# show result
if result:

    # showing result, it take frame name and image
    # output
    imshow("GeeksForGeeks", image)

    # saving image in local storage
    imwrite("GeeksForGeeks.png", image)

    # If keyboard interrupt occurs, destroy image
    # window
    waitKey(0)
    destroyWindow("GeeksForGeeks")

# If captured image is corrupted, moving to else part
else:
    print("No image detected. Please! try again")
```

**输出:**

![](img/973db22f30349633a56800269e6c1300.png)

## **方法二:使用 PyGame**

PyGame.camera()相机初始化器仅支持 Linux 操作系统，目前与 Windows 不兼容。要在 Linux 中安装 [PyGame](https://www.geeksforgeeks.org/install-pygame-in-linux/) ，在 Linux 终端输入以下命令。

### **进场:**

1.导入 pygame.camera 模块

2.使用 camera.init()方法初始化摄像机。

## 蟒蛇 3

```
pygame.camera.init()
```

3。使用 list _ cameras()方法检测所有可用的摄像机。

## 蟒蛇 3

```
camlist = pygame.camera.list_cameras()
```

4。检查是否检测到摄像头

**语法:**

```
if camlist:

    # Initialize and start camera  
    cam = pygame.camera.Camera(camlist[0], (640, 480))
    cam.start()

    # capturing the single image
    image = cam.get_image()

    # saving the image
    pygame.image.save(image, "filename.jpg")

else:
    if camera is not detected the moving to this part
```

#### **示例:**

## 蟒蛇 3

```
# Python program to capture a single image
# using pygame library

# importing the pygame library
import pygame
import pygame.camera

# initializing  the camera
pygame.camera.init()

# make the list of all available cameras
camlist = pygame.camera.list_cameras()

# if camera is detected or not
if camlist:

    # initializing the cam variable with default camera
    cam = pygame.camera.Camera(camlist[0], (640, 480))

    # opening the camera
    cam.start()

    # capturing the single image
    image = cam.get_image()

    # saving the image
    pygame.image.save(image, "filename.jpg")

# if camera is not detected the moving to else part
else:
    print("No camera on current device")
```

**输出:**

![](img/973db22f30349633a56800269e6c1300.png)