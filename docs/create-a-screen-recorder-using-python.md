# 使用 Python 创建屏幕记录器

> 原文:[https://www . geesforgeks . org/create-a-screen-recorder-use-python/](https://www.geeksforgeeks.org/create-a-screen-recorder-using-python/)

Python 是一种广泛使用的通用语言。它允许执行各种任务。其中一个可以录制视频。它提供了一个名为 **pyautogui** 的模块，可以用于相同的目的。该模块与 NumPy 和 OpenCV 一起提供了操作和保存图像的方法(本例中为截图)

### 需要的模块

*   [**Numpy:**](https://www.geeksforgeeks.org/python-numpy/) 要安装 Numpy，请在终端中键入以下命令。

```
pip install numpy

```

*   **pyautogui:** 要安装 pyautogui，请在终端中键入以下命令。

```
pip install pyautogui

```

*   [**OpenCV:**](https://www.geeksforgeeks.org/opencv-python-tutorial/) 要安装 OpenCV，请在终端中键入以下命令。

```
pip install opencv-python
```

下面是实现。

首先，导入所有必需的包。

## 蟒蛇 3

```
# importing the required packages
import pyautogui
import cv2
import numpy as np
```

现在，在录制屏幕之前，我们必须创建一个 VideoWriter 对象。此外，我们必须指定输出文件名、视频编解码器、FPS 和视频分辨率。在视频编解码中，我们要指定一个 4 字节的代码(比如 XVID、MJPG、X264 等。).我们将在这里使用 XVID。

## 蟒蛇 3

```
# Specify resolution
resolution = (1920, 1080)

# Specify video codec
codec = cv2.VideoWriter_fourcc(*"XVID")

# Specify name of Output file
filename = "Recording.avi"

# Specify frames rate. We can choose 
# any value and experiment with it
fps = 60.0

# Creating a VideoWriter object
out = cv2.VideoWriter(filename, codec, fps, resolution)
```

**可选:**要实时显示录制内容，我们必须创建一个空窗口并调整其大小。

## 蟒蛇 3

```
# Create an Empty window
cv2.namedWindow("Live", cv2.WINDOW_NORMAL)

# Resize this window
cv2.resizeWindow("Live", 480, 270)
```

现在，让我们开始录制我们的屏幕。我们将运行一个无限循环，在循环的每次迭代中，我们将拍摄一个截图，并在视频编写器的帮助下将其写入输出文件。

## 蟒蛇 3

```
while True:

    # Take screenshot using PyAutoGUI
    img = pyautogui.screenshot()

    # Convert the screenshot to a numpy array
    frame = np.array(img)

    # Convert it from BGR(Blue, Green, Red) to
    # RGB(Red, Green, Blue)
    frame = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    # Write it to the output file
    out.write(frame)

    # Optional: Display the recording screen
    cv2.imshow('Live', frame)

    # Stop recording when we press 'q'
    if cv2.waitKey(1) == ord('q'):
        break
```

一切完成后，我们将释放编写器并销毁 OpenCV 打开的所有窗口。

## 蟒蛇 3

```
# Release the Video writer
out.release()

# Destroy all windows
cv2.destroyAllWindows()
```

**完整代码:**

## 蟒蛇 3

```
# importing the required packages
import pyautogui
import cv2
import numpy as np

# Specify resolution
resolution = (1920, 1080)

# Specify video codec
codec = cv2.VideoWriter_fourcc(*"XVID")

# Specify name of Output file
filename = "Recording.avi"

# Specify frames rate. We can choose any 
# value and experiment with it
fps = 60.0

# Creating a VideoWriter object
out = cv2.VideoWriter(filename, codec, fps, resolution)

# Create an Empty window
cv2.namedWindow("Live", cv2.WINDOW_NORMAL)

# Resize this window
cv2.resizeWindow("Live", 480, 270)

while True:
    # Take screenshot using PyAutoGUI
    img = pyautogui.screenshot()

    # Convert the screenshot to a numpy array
    frame = np.array(img)

    # Convert it from BGR(Blue, Green, Red) to
    # RGB(Red, Green, Blue)
    frame = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)

    # Write it to the output file
    out.write(frame)

    # Optional: Display the recording screen
    cv2.imshow('Live', frame)

    # Stop recording when we press 'q'
    if cv2.waitKey(1) == ord('q'):
        break

# Release the Video writer
out.release()

# Destroy all windows
cv2.destroyAllWindows()
```

**输出:**

<video class="wp-video-shortcode" id="video-480516-1" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200904163506/screen-recorder-python.webm?_=1">[https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200904163506/screen-recorder-python.webm](https://media.geeksforgeeks.org/wp-content/cdn-uploads/20200904163506/screen-recorder-python.webm)</video>