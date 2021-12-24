# 如何使用 Python 让 PC 自动保持清醒？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 自动保持电脑清醒/](https://www.geeksforgeeks.org/how-to-keep-your-pc-awake-automatically-using-python/)

在本文中，我们将讨论如何使用 Python 让您的电脑保持清醒。为了执行这个任务，我们将使用一个外部 Python 模块。

这里我们将使用一个 python 包 *PyAutoGUI* (跨平台 GUI 自动化 Python 模块用来编程控制鼠标&键盘。)这将使您的电脑永远保持清醒，直到您关闭程序。使用以下命令安装该模块:

```py
pip install pyautogui
```

安装模块后执行以下程序:

## python 3

```py
# Import required modules
import pyautogui
import time

# FAILSAFE to FALSE feature is enabled by default 
# so that you can easily stop execution of 
# your pyautogui program by manually moving the 
# mouse to the upper left corner of the screen. 
# Once the mouse is in this location,
# pyautogui will throw an exception and exit.
pyautogui.FAILSAFE = False

# We want to run this code for infinite 
# time till we stop it so we use infinite loop now
while True:

    # time.sleep(t) is used to give a break of 
    # specified time t seconds so that its not 
    # too frequent
    time.sleep(15)

    # This for loop is used to move the mouse 
    # pointer to 500 pixels in this case(5*100)
    for i in range(0, 100):
        pyautogui.moveTo(0, i * 5)

    # This for loop is used to press keyboard keys,
    # in this case the harmless key shift key is 
    # used. You can change it according to your 
    # requirement. This works with all keys.
    for i in range(0, 3):
        pyautogui.press('shift')
```

在执行上述程序时，您会看到在 *time.sleep()* 中的指定时间后，鼠标指针移动到最左上角(也可以通过提及 *pyautogui.moveTo()* 中的坐标来自定义该位置)并开始向下移动。