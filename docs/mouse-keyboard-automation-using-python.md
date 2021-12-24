# 使用 Python 的鼠标和键盘自动化

> 原文:[https://www . geesforgeks . org/鼠标-键盘-自动化-使用-python/](https://www.geeksforgeeks.org/mouse-keyboard-automation-using-python/)

本文说明了如何使用 python 中的 **pyautogui** 模块来自动移动鼠标和键盘。本模块未预装 python。因此要安装它，请运行以下命令:

```py
 pip3 install pyautogui
```

**使用 pyautogui 模块控制鼠标移动**

Python 使用屏幕的坐标系来跟踪和控制鼠标。假设你的屏幕分辨率是 1920X1080，那么你的屏幕坐标系看起来是这样的:

![gui in python](img/eb2d6633a5cf12f88197b769c1a85719.png)

*   **size():** 此功能用于获取屏幕分辨率。

## 计算机编程语言

```py
import pyautogui
print(pyautogui.size())
```

用保存此文件。py 扩展名，然后运行文件。
这个 python 代码使用 size()函数以 x，y 格式输出你的屏幕分辨率:
输出:

```py
 (1920, 1080)
```

注意:本文中提供的一些代码可能无法在 geesforgeks IDE 上运行，因为 geesforgeks IDE 没有运行这些代码所需的模块。但是通过安装 python 并按照文章中提供的说明，这些代码可以很容易地在您的 PC 上本地运行。

*   **moveTo():** 使用此功能在 pyautogui 模块中移动鼠标。

## 计算机编程语言

```py
import pyautogui
pyautogui.moveTo(100, 100, duration = 1)
```

这段代码使用 moveTo()函数，该函数接受 x 和 y 坐标，以及一个可选的持续时间参数。该函数将鼠标指针从其当前位置移动到 x，y 坐标，并按照 duration 参数的指定花费时间。保存并运行这个 python 脚本，看到鼠标指针神奇地从当前位置移动到坐标(100，100)，这个过程需要 1 秒钟。

*   **moveRel()函数:**将鼠标指针相对于其先前位置移动。

## 计算机编程语言

```py
import pyautogui
pyautogui.moveRel(0, 50, duration = 1)
```

这段代码将鼠标指针相对于其原始位置移动(0，50)。例如，如果运行代码前的鼠标位置是(1000，1000)，那么这段代码将在 1 秒内将指针移动到坐标(1000，1050)。

*   **位置():**功能获取鼠标指针的当前位置。

## 计算机编程语言

```py
import pyautogui
print(pyautogui.position())
```

输出:执行程序时鼠标所在的坐标。

*   **点击():**用于点击和拖动鼠标的功能。

## 计算机编程语言

```py
import pyautogui
pyautogui.click(100, 100)
```

这段代码在位置(100，100)执行典型的鼠标点击。
我们有两个与鼠标拖动操作相关的功能， **dragTo 和 dragRel** 。它们执行类似于 moveTo 和 moveRel 的功能，只是它们在移动时按住鼠标左键，从而启动拖动。
这个功能可以用在各种地方，比如移动对话框，或者在 MS Paint 中使用铅笔工具自动绘制一些东西。用颜料画一个正方形:

## 计算机编程语言

```py
import time

# a module which has functions related to time.
# It can be installed using cmd command:
# pip install time, in the same way as pyautogui.
import pyautogui
time.sleep(10)

# makes program execution pause for 10 sec
pyautogui.moveTo(1000, 1000, duration = 1)

# moves mouse to 1000, 1000.
pyautogui.dragRel(100, 0, duration = 1)

# drags mouse 100, 0 relative to its previous position,
# thus dragging it to 1100, 1000
pyautogui.dragRel(0, 100, duration = 1)
pyautogui.dragRel(-100, 0, duration = 1)
pyautogui.dragRel(0, -100, duration = 1)
```

在运行代码之前，选择铅笔工具，在背景中打开 MS paint。现在运行代码，在 10 秒之前快速切换到 MS paint(因为我们在运行程序之前已经使用 sleep()函数给出了 10 秒的暂停时间)。
10 秒后，你会看到一个用 MS paint 绘制的正方形，左上角边缘为 1000、1000，边缘长度为 100 像素。

*   **scroll():** scroll 函数以像素数为自变量，将屏幕向上滚动到给定的像素数。

## 计算机编程语言

```py
import pyautogui
pyautogui.scroll(200)
```

该代码将活动屏幕滚动到 200 像素。

*   **打字机():**您可以使用打字机()功能自动输入字符串。只需传递您想要作为此函数的参数键入的字符串。

## 计算机编程语言

```py
import pyautogui
pyautogui.click(100, 100)
pyautogui.typewrite("hello Geeks !")
```

假设屏幕上坐标 100，100 处有一个文本字段，那么这段代码将点击文本字段使其激活，并键入“你好，极客！”在里面。

*   **传递键名:**可以通过 typewrite()函数单独传递键名。

## 计算机编程语言

```py
import pyautogui
pyautogui.typewrite(["a", "left", "ctrlleft"])
```

该代码相当于自动键入“a”，按下左箭头键，然后按下左控制键。

*   **按热键组合:**使用热键()功能按 ctrl-c、ctrl-a 等组合键。

## 计算机编程语言

```py
import pyautogui
pyautogui.hotkey("ctrlleft", "a")
```

这个代码自动等同于同时按下左 ctrl 和“a”。因此，在窗口中，这将导致选择屏幕上出现的所有文本。

**示例:**

在 WhatsApp 中发送消息并自动为所有人删除。你需要已经在 chrome 中打开了 Whatsapp，才能运行这个。运行完这段代码后，打开 chrome 上的 WhatsApp 选项卡。

## 蟒蛇 3

```py
import pyautogui as pg
import time

def delete_for_everyone():
    pg.click(807, 979)
    pg.typewrite("hello")
    pg.typewrite(["enter"])
    time.sleep(2)
    pg.click(1621, 896)
    pg.click(1621, 896)

    # time.sleep(1)
    pg.click(1693, 859)

    # time.sleep(1)
    pg.click(1014, 669)

    # time.sleep(1)
    pg.click(1111, 605)

a=20
time.sleep(10)
while(a!=0):
    delete_for_everyone()
    a=a-1
```

本文由 **tkkhhaarree** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](https://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。