# 如何在 Kivy–Python 中添加自定义字体？

> 原文:[https://www . geesforgeks . org/如何添加自定义字体-in-kivy-python/](https://www.geeksforgeeks.org/how-to-add-custom-fonts-in-kivy-python/)

**先决条件:** [基维教程](https://www.geeksforgeeks.org/kivy-tutorial/)

Kivy 是 Python 中独立于平台的 GUI 工具。它可以在安卓、IOS、Linux 和 Windows 等平台上运行。这是 python 中唯一一个可以在安卓设备上独立运行的图形用户界面库，即使我们也可以在树莓 pi 上使用它。它是一个开源的 Python 库，用于快速开发多点触控应用程序。它的图形引擎建立在 OpenGL 之上，支持快速图形流水线。

在本文中，我们将使用 Python 的 kivy 框架开发一个 GUI 窗口，并且我们将在这个窗口上添加一个按钮，并且我们将在这个按钮的文本上添加我们自己的字体样式。对于这个任务，你应该有一个自定义的字体样式，不要担心，如果你没有你的，你可以从这个链接下载，你会得到大量的字体样式，你也可以下载并解压它们。解压后，你会得到文件。ttf 格式保留这些文件，因为它们保存了实际的字体样式。

**循序渐进法:**

在 kivy 应用程序中使用自定义字体的基本方法:

*   导入按钮
*   导入 kivyApp
*   导入标签库
*   导入生成器
*   创建应用程序类
*   返回布局
*   运行类的实例

**实施:**

## 蟒蛇 3

```py
# importing button widget from kivy framework
from kivy.uix.button import Button
from kivy.app import App

# importing labelbase which which 
# register our custom font for application
from kivy.core.text import LabelBase
from kivy.lang import Builder

# this is the main class which will
# render the whole application
class uiApp(App):

    # method which will render our application
    def build(self):
        return Builder.load_string("""

# adding our button
Button:

    # text which will appear on first button
    text:"first button"

    # specifying the fontstyle name that we 
    # have registered in main.py file
    font_name:"Lemonada"
    font_size:65
                                   """)

# registering our new custom fontstyle
LabelBase.register(name='Lemonada', 
                   fn_regular='Lemonada-VariableFont_wght.ttf')

# running the application
uiApp().run()
```

**输出:**

<video class="wp-video-shortcode" id="video-553448-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210204123848/customfontupdated.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210204123848/customfontupdated.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210204123848/customfontupdated.mp4)</video>