# 如何在 Tkinter 中的任意位置放置按钮？

> 原文:[https://www . geesforgeks . org/how-to-place-a-button-at-in-tkinter/](https://www.geeksforgeeks.org/how-to-place-a-button-at-any-position-in-tkinter/)

**先决条件:** [在 Tkinter](https://www.geeksforgeeks.org/python-creating-a-button-in-tkinter/) 中创建按钮

**Tkinter** 是 Python 中开发 GUI(图形用户界面)最常用的库。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 为开发图形用户界面提供了多种选择。在所有的图形用户界面方法中， *tkinter* 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。Python 搭配 *tkinter* 是创建 GUI 应用程序最快最简单的方法。使用 *tkinter* 创建图形用户界面是一项简单的任务。

**进场:**

*   导入 *tkinter* 模块
*   创建主窗口
*   在窗口中添加一个按钮。
*   按下按钮。

*tkinter* 模块中的按钮可以通过两种方式放置或移动到任意位置:

*   通过使用 *place()* 方法。
*   并且通过使用 *pack()* 方法。

**方法 1:** 使用[地点()](https://www.geeksforgeeks.org/python-place-method-in-tkinter/)方法

此方法用于将按钮放置在绝对定义的位置。

> **语法:** button1.place(x=some_value，y=some_value)
> 
> **参数:**
> 
> *   **x :** 定义按钮位置的 x 坐标。
> *   **y :** 定义按钮位置的 y 坐标。

下面是上面显示的方法的实现:

## 蟒蛇 3

```py
# Importing tkinter module 
from tkinter import *        

# Creating a tkinter window
root = Tk() 

# Initialize tkinter window with dimensions 300 x 250             
root.geometry('300x250')     

# Creating a Button
btn = Button(root, text = 'Click me !', command = root.destroy)

# Set the position of button to coordinate (100, 20)
btn.place(x=100, y=20)

root.mainloop()
```

**输出:**

![](img/0f32863e9eed1c6069eae645e8871463.png)

**方法 2:** 使用[包()](https://www.geeksforgeeks.org/python-pack-method-in-tkinter/)方法

此方法用于将按钮放置在相对位置。

> **语法:** button1.pack(side=some_side，padx=some_value，pady=some_value)
> 
> **参数:**
> 
> *   **边:**定义按钮将要放置的边。
> *   **padx :** 从定义的一侧定义 x 轴上的填充。
> *   **pady :** 定义 y 轴上从定义侧开始的填充。

下面是上面显示的方法的实现:

## 蟒蛇 3

```py
# Importing tkinter module 
from tkinter import *        

# Creating a tkinter window
root = Tk() 

# Initialize tkinter window with dimensions 300 x 250             
root.geometry('300x250')     

# Creating a Button
btn = Button(root, text = 'Click me !', command = root.destroy)

# Set a relative position of button
btn.pack(side=RIGHT, padx=15, pady=20)

root.mainloop()
```

**输出:**

![](img/6757f4f1518f15be2ab6f29c60ea7552.png)