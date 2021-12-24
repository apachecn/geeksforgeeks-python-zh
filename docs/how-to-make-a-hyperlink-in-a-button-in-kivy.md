# 如何在 Kivy 中的按钮中制作超链接？

> 原文:[https://www . geeksforgeeks . org/如何在 kivy 中制作按钮超链接/](https://www.geeksforgeeks.org/how-to-make-a-hyperlink-in-a-button-in-kivy/)

Kivy 是 Python 中独立于平台的 GUI 工具。它可以在安卓、IOS、Linux 和 Windows 等平台上运行。这是唯一一个可以在安卓设备上独立运行的 python 图形用户界面库，即使我们也可以在树莓皮上使用它。如果你是新手，你可以从这个[链接](https://www.geeksforgeeks.org/kivy-tutorial/)中学习。

在本文中，我们将使用 Python 的 kivy 框架开发一个 GUI 窗口，我们将在这个窗口上添加一个按钮。通常情况下，我们将一个方法附加到一个按钮上，整个方法在另一个 python 文件中定义，但是这次我们将使用相同的 kivy 字符串编写 python 的按钮代码。

**注意:**我们在这里使用 on_release 事件和按钮来使其起作用。我们也可以使用 on_press 事件，而不是 on_release 事件，这两个事件都可以打开链接，唯一的区别是 on_release 事件会在我们从按钮上释放手指时打开链接，而 on_press 会在我们触摸按钮后立即打开链接。要使用 on_press 事件，只需将 on_release 替换为 on_press。

这里，我们要使用的 IDE 是 pycharm，我们要使用的 python 版本是 python 3.6。

**实施**

## 蟒蛇 3

```
# importing button widget from kivy framework
from kivy.uix.button import Button

from kivy.app import App

# importing builder from kivy
from kivy.lang import Builder

# this is the main class which will render the whole application
class uiApp(App):

    # method which will render our application
    def build(self):
        return Builder.load_string("""

Button:

    # text which will appear on button
    text:"click here to open google search"

    on_release:

        # importing webbrowser module
        import webbrowser

        # it will open google window in your browser
        webbrowser.open('http://www.google.com')

        print("see like this way you can write python supported code in kivy file")

                                   """)

# running the application
uiApp().run()
```

**输出:**

<video class="wp-video-shortcode" id="video-557089-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210204133102/brow.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210204133102/brow.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210204133102/brow.mp4)</video>