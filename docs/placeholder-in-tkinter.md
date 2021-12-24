# Tkinter 中的占位符

> 原文:[https://www.geeksforgeeks.org/placeholder-in-tkinter/](https://www.geeksforgeeks.org/placeholder-in-tkinter/)

**先决条件:**

*   [**Python GUI–tkinter**](https://www.geeksforgeeks.org/python-gui-tkinter/)
*   [**绑定–Tkit**](https://www.geeksforgeeks.org/python-binding-function-in-tkinter/)

Python 为开发图形用户界面提供了多个选项。在所有的 GUI 方法中，tkinter 是最常用的方法。它是 Python 附带的 Tk 图形用户界面工具包的标准 Python 接口。

什么是占位符，如何使用 tkinter 实现占位符:

在编程中，占位符可以是一个字符、单词或字符串，它短暂地代替了最终数据。例如，一个应用科学家可能认识到她想要一个精确的数值或变量范围，然而却不知道输入什么。

Placeholder 属性用于给出提示，告知输入字段期望什么输入，或者我们可以说它将给出在用户输入值之前显示在输入字段中的简短提示。

在 Tkinter 中，占位符没有内置的方法或属性，但它仍然可以使用模块的内置函数来执行。

**进场:**

*   导入模块
*   创建正常 Tkinter 窗口
*   添加条目框

**语法:**

> 条目(对象名，* *属性)

*   添加占位符，这里使用 insert()完成，然后将占位符绑定到框中

**语法:**

> 插入(索引)

*   执行代码

**程序:**

## 蟒蛇 3

```
# Import Module
from tkinter import *

# Create Tkinter Object
root = Tk()

# Set geometry
root.geometry('400x400')

# call function when we click on entry box
def click(*args):
    playlist_url.delete(0, 'end')

# call function when we leave entry box
def leave(*args):
    playlist_url.delete(0, 'end')
    playlist_url.insert(0, 'Enter Text:- ')
    root.focus()

# Add Entry Box
playlist_url = Entry(root, width=60)

# Add text in Entry box
playlist_url.insert(0, 'Enter Text:- ')
playlist_url.pack(pady=10)

# Use bind method
playlist_url.bind("<Button-1>", click)
playlist_url.bind("<Leave>", leave)

# Execute Tkinter
root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-542738-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210113114450/FreeOnlineScreenRecorderProject5.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210113114450/FreeOnlineScreenRecorderProject5.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210113114450/FreeOnlineScreenRecorderProject5.mp4)</video>