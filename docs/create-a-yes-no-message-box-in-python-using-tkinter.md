# 使用 tkinter

在 Python 中创建是/否消息框

> 原文:[https://www . geesforgeks . org/create-a-yes-no-message-box-in-python-using-tkinter/](https://www.geeksforgeeks.org/create-a-yes-no-message-box-in-python-using-tkinter/)

Python 提供了许多图形用户界面(GUI)框架，但 Tk 界面或[Tinter](https://www.geeksforgeeks.org/python-gui-tkinter/)是使用最广泛的框架。它是跨平台的，允许相同的代码运行，而与操作系统平台(视窗、Linux 或苹果操作系统)无关。Tkinter 重量轻，速度快，使用简单。Tkinter 提供了多种小部件，可以使用标准属性和几何管理方法进行定制。Tkinter 消息框可用于向用户提问或显示消息。

**注意:**更多信息请参考[Python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

创建 tkinter 消息框的步骤:

1.  **Import tkinter module**

    ```py
    import tkinter as tk
    from tkinter import *
    ```

    **注意:**Python 2 . x 中模块的名称为‘Tkinter’，Python 3.x 中为‘Tkinter’。这里使用的是 Python 3.x。

2.  **导入 tkinter messagebox 构件**

    ```py
    from tkinter import messagebox as mb
    ```

3.  **Create the method that is called to display the Yes/No Message Box**

    ```py
    def call():
        res=mb.askquestion('Exit Application', 'Do you really want to exit')
        if res == 'yes' :
            root.destroy()
        else :
            mb.showinfo('Return', 'Returning to main application')

    ```

    **解释:**
    **句法:**

    ```py
    askquestion(title=None, message=None, **options) 
    ```

    **参数**

    *   **标题:**用于给出一个名称，显示在对话框的标题中。
    *   **消息:**为用户提问。

    **返回值:**点击是选项返回‘是’，点击否选项返回‘否’。

    **语法:**

    ```py
    showinfo(title=None, message=None, **options)
    ```

    **参数**

    *   **标题:**用于给出一个名称，显示在对话框的标题中。
    *   **消息:**用户信息。

    **语法:**

    ```py
    destroy() 
    ```

    此方法会破坏一个小部件。

4.  **Create the canvas for the button will be placed**

    ```py
    root=tk.Tk()
    canvas=tk.Canvas(root, width=200, height=200)
    canvas.pack()

    ```

    **解释:**
    **句法:**

    ```py
    Tk(screenName=None,  baseName=None,  className=’Tk’,  useTk=1)
    ```

    用于创建父窗口。Tk 类被实例化，没有任何参数。通过更改类名参数的值，可以将父窗口的名称更改为所需的名称。这里的“根”是父窗口。

    **语法:**

    ```py
    Canvas(master, option=value)
    ```

    **参数:**

    *   **主:**用于表示父窗口。这里的‘根’就是主人。
    *   **选项:**用于指定边框、背景色、高度、宽度等。

    **返回值:**方法返回一个字符串(。！画布)。

    **语法:**

    ```py
    pack(**options) 
    ```

    在将小部件放入父小部件之前，以块的形式组织小部件。这些选项可用于展开、填充和指定边(左、右、上、下)

5.  **Create the button and place it inside the canvas**

    ```py
    b=Button(root, text='Quit Application', command=call)
    canvas.create_window(100, 100, window=b)

    ```

    **解释:**
    **句法:**

    ```py
    Button(master=None, options)
    ```

    **参数:**

    *   **主:**这里根是父窗口。
    *   **选项:**有许多受支持的选项。这种情况下使用的选项是文本和命令。
        *   **文本:**按钮文本
        *   **命令:**按下按钮时要调用的动作或方法。

    **返回值:**方法返回一个字符串(。！按钮)。

    **语法:**

    ```py
    create_window(x, y, **options)
    ```

    **参数:**

    *   **x，y:** 指定小部件(按钮)在画布中的位置。
    *   **选项:**支持多种选项，如锚点、高度、宽度、状态、标签、窗口。这里使用的选项是 window。
        *   **窗口:**窗口=b 其中 b 是要放置在画布上的小部件(按钮)。

    **返回值:**返回窗口对象的对象标识。

6.  **Call the mainloop() method**

    ```py
    root.mainloop()

    ```

    **解释:**
    **句法:**

    ```py
    mainloop()
    ```

    这是一个无限循环，当程序准备运行时调用。它等待一个事件(鼠标点击)发生，一旦接收到该事件，就处理该事件。只要父窗口没有被破坏，mainloop()就会运行。

**完整程序如下:**

```py
# Python program to create 
# yes/no message box

import tkinter as tk
from tkinter import * 
from tkinter import messagebox as mb

def call():
    res = mb.askquestion('Exit Application', 
                         'Do you really want to exit')

    if res == 'yes' :
        root.destroy()

    else :
        mb.showinfo('Return', 'Returning to main application')

# Driver's code
root = tk.Tk()
canvas = tk.Canvas(root, 
                   width = 200, 
                   height = 200)

canvas.pack()
b = Button(root,
           text ='Quit Application',
           command = call)

canvas.create_window(100, 100, 
                     window = b)

root.mainloop()
```

**输出:**

<video class="wp-video-shortcode" id="video-385355-1" width="665" height="376" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200310124158/outputmsgbox_Trim1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200310124158/outputmsgbox_Trim1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200310124158/outputmsgbox_Trim1.mp4)</video>