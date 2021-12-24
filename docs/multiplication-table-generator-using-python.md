# 使用 Python 的乘法表生成器

> 原文:[https://www . geesforgeks . org/乘法表-生成器-使用-python/](https://www.geeksforgeeks.org/multiplication-table-generator-using-python/)

**先决条件:**[**Python GUI-Tkinter**](https://www.geeksforgeeks.org/python-gui-tkinter/)

我们都知道 Tkinter 是 Python 的标准 GUI 库。Python 与 Tkinter 相结合，为创建图形用户界面应用程序提供了一种快速简单的方法。在本文中，我们将学习如何使用 Tkinter 创建一个时间表。

**进场:**

*   导入 Tkinter 库
*   创建乘法表的函数
*   创建主窗口(容器)
*   创建存储数字值的可变文本字段
*   通过生成表格按钮调用函数
*   执行代码

**程序:**

## 计算机编程语言

```
#import library
import sys
from tkinter import *

def MultiTable():

    print("\n:Multiplication Table:\n")
    print("\nTimes-Table of Number", (EnterTable.get()), '\n')

    for x in range(1, 13):
        number = int(EnterTable.get())
        print('\t\t', (number), 'x', (x), '=', (x*number),)

# Create Main window
Table = Tk()
Table.geometry('250x250+700+200')
Table.title('Multiplication Table')

# Variable Declaration
EnterTable = StringVar()

label1 = Label(Table, text='Enter Your Times-table Number:',
               font=30, fg='Black').grid(row=1, column=6)
label1 = Label(Table, text='                     ').grid(row=2, column=6)

# Store Number in Textvariable
entry = Entry(Table, textvariable=EnterTable,
              justify='center').grid(row=3, column=6)
label1 = Label(Table, text='                     ').grid(row=4, column=6)

# Call the function
button1 = Button(Table, text="Generate Table", fg="Blue",
                 command=MultiTable).grid(row=5, column=6)
label1 = Label(Table, text='                     ').grid(row=6, column=6)

# Exit
EXIT = Button(Table, text="Quit", fg="red",
              command=Table.destroy).grid(row=7, column=6)

Table.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-560448-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210215161358/Screen-Recording-2021-02-15-at-4.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210215161358/Screen-Recording-2021-02-15-at-4.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210215161358/Screen-Recording-2021-02-15-at-4.mp4)</video>