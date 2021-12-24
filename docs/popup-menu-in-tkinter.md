# tkinter 中的弹出式菜单

> 原文:[https://www.geeksforgeeks.org/popup-menu-in-tkinter/](https://www.geeksforgeeks.org/popup-menu-in-tkinter/)

[Tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/) 是 Python 的标准 GUI(图形用户界面)包。它是 Python 本身附带的图形用户界面应用程序最常用的包之一。

**注意:**更多信息请参考[Python GUI–tkinter](https://www.geeksforgeeks.org/python-gui-tkinter/)

#### 菜单小部件

菜单是任何图形用户界面的重要组成部分。菜单的一个常见用途是提供对各种操作的便捷访问，如保存或打开文件、退出程序或操作数据。顶层菜单显示在根窗口或任何其他顶层窗口的标题栏下方。

**语法:**

```
menu = Menu(master, **options)
```

**注意:**更多信息请参考 Tkinter 中的 [Python |菜单小工具](https://www.geeksforgeeks.org/python-menu-widget-in-tkinter/)

#### 弹出菜单

弹出式菜单是出现在用户交互中的上下文菜单。该菜单可以显示在客户端窗口的任何地方。下面是使用 Tkinter 库创建弹出菜单的 python 代码。

```
#creating popup menu in tkinter
import tkinter

class A:
    #creates parent window
    def __init__(self):

        self.root = tkinter.Tk()
        self.root.geometry('500x500')

        self.frame1 = tkinter.Label(self.root,
                                    width = 400,
                                    height = 400,
                                    bg = '#AAAAAA')
        self.frame1.pack()

    #create menu
    def popup(self):
        self.popup_menu = tkinter.Menu(self.root,
                                       tearoff = 0)

        self.popup_menu.add_command(label = "say hi",
                                    command = lambda:self.hey("hi"))

        self.popup_menu.add_command(label = "say hello",
                                    command = lambda:self.hey("hello"))
        self.popup_menu.add_separator()
        self.popup_menu.add_command(label = "say bye",
                                    command = lambda:self.hey("bye"))

    #display menu on right click
    def do_popup(self,event):
        try:
            self.popup_menu.tk_popup(event.x_root,
                                     event.y_root)
        finally:
            self.popup_menu.grab_release()

    def hey(self,s):
        self.frame1.configure(text = s)

    def run(self):
        self.popup()
        self.root.bind("<Button-3>",self.do_popup)
        tkinter.mainloop()

a = A()
a.run()
```

**输出:**

<video class="wp-video-shortcode" id="video-387271-1" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20200320200303/python-tkinter-pop-up-menu.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200320200303/python-tkinter-pop-up-menu.webm](https://media.geeksforgeeks.org/wp-content/uploads/20200320200303/python-tkinter-pop-up-menu.webm)</video>

右键单击会出现上述代码中的弹出菜单。

**功能**

*   **菜单(根):**创建菜单。
*   **add_command(label，command):** 添加菜单上的命令，当单击该选项时，命令参数调用函数 hey()。
*   **add_separator():** 添加分隔符。
*   **tk_popup(x，y):** 在给定的参数位置发布菜单
*   **grab_release():** 释放事件抓取
*   **绑定(键，事件):**绑定鼠标事件。