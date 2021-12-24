# 使用 Tkinter 模块的事实应用程序

> 原文:[https://www . geesforgeks . org/facts-app-using-tkinter-module/](https://www.geeksforgeeks.org/facts-app-using-tkinter-module/)

这是一个应用程序，将为我们提供事实。有了 Python，我们可以让事情变得非常简单。我们有一个非常惊人的图书馆，这样我们就可以做它。

我们只需要两个库，如果我们把这个概念结合起来，我们就能做出一个新的东西。我们只需要使用 *tkinter* 和 *randfacts* 就可以做到这一点。

#### 需要模块

*   **Tkinter:**Tkinter 包(“Tk 接口”)是 Tk GUI 工具包的标准 Python 接口。它是 python 中的一个内置模块。
*   **RandFacts:** Randfacts 是一个生成随机事实的 python 库。您可以使用 *randfacts.getFact()* 返回一个随机有趣的事实。使用以下命令在系统中安装此模块。

```
pip install randfacts

```

我们必须导入库，并制作两个按钮，一个用于添加事实，一个用于清除窗口。

#### 逐步方法:

**步骤 1)** 导入模块。

## 蟒蛇 3

```
# import required modules
import tkinter as tk
from tkinter import *
import randfacts
import time
```

**步骤 2)** 进行移动功能(用于添加事实)

## 蟒蛇 3

```
# function to add facts
def move():
    facts = randfacts.getFact(True)
    c = "*)"
    label = Label(root, text=c+facts)
    label.pack()
```

**步骤 3)** 进行清除窗口的破坏功能

## 蟒蛇 3

```
# function to close window
def destroy():
    root.destroy()
```

**步骤 3)** 在驱动程序代码中创建按钮。

## 蟒蛇 3

```
# driver code
root = tk.Tk()

# adjust window
root.config(bg="red")
root.geometry("400x400")

# add buttons
button = tk.Button(root, text="Click here for Facts", command=move)
button2 = tk.Button(root, text="Clear and quit", command=destroy)
button.pack()
button2.pack()

root.mainloop()
```

**以下是基于上述方法的完整程序:**

## 蟒蛇 3

```
# import required modules
import tkinter as tk
from tkinter import *
import randfacts
import time

# function to add facts
def move():
    facts = randfacts.getFact(True)
    c = "*)"
    label = Label(root, text=c+facts)
    label.pack()

# function to close window
def destroy():
    root.destroy()

# driver code
root = tk.Tk()

# adjust window
root.config(bg="red")
root.geometry("400x400")

# add buttons
button = tk.Button(root, text="Click here for Facts", command=move)
button2 = tk.Button(root, text="Clear and quit", command=destroy)
button.pack()
button2.pack()

root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-514041-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201115204925/factapp.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201115204925/factapp.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201115204925/factapp.mp4)</video>