# 如何在 Kivy 文件中直接运行 Python 脚本？

> 原文:[https://www . geesforgeks . org/how-run-python-script-direct-in-kivy-file/](https://www.geeksforgeeks.org/how-to-run-python-script-directly-in-kivy-file/)

Kivy 是 Python 中独立于平台的 GUI 工具。它可以在安卓、IOS、Linux 和 Windows 等平台上运行。这是 python 中唯一一个可以在安卓设备上独立运行的图形用户界面库，即使我们也可以在树莓 pi 上使用它。这是一个开源的 Python 库，用于快速开发利用创新用户界面的应用程序，例如多点触控应用程序。它的图形引擎建立在 OpenGL ES 2 之上，并且有快速的图形流水线。如果你是新手，你可以从这个[链接](https://www.geeksforgeeks.org/kivy-tutorial/)中学习。

在本文中，我们将使用 python 的 kivy 框架开发一个 GUI 窗口，并且我们将在这个窗口上添加一个按钮。通常情况下，我们将一个方法附加到一个按钮上，整个方法在另一个 python 文件中定义，但这次我们将向其中添加按钮代码。kv 文件

我们要用的 IDE 是 pycharm，要用的 python 版本是 python 3.6。

### 方法

*   在 pycharm 中创建新项目
*   安装所需的软件包
*   在项目的 venv 目录中添加新的 python 文件。添加文件视频已附加。

<video class="wp-video-shortcode" id="video-553006-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210202201343/main-file-maker.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210202201343/main-file-maker.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210202201343/main-file-maker.mp4)</video>

*   添加新的。项目中的 kv 文件。这里描述了我们的实现:

<video class="wp-video-shortcode" id="video-553006-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210202201440/ui-file-maker.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210202201440/ui-file-maker.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210202201440/ui-file-maker.mp4)</video>

*   向两个文件添加代码

> main.py

## 蟒蛇 3

```
# importing image widget of kivy framework
from kivy.uix.image import Image
from kivy.uix.button import Button
from kivy.app import App

# importing boxlayout for our application
from kivy.uix.boxlayout import BoxLayout

# this will connect MainWindow which we have created in ui.kv with main.py file
class MainWindow(BoxLayout):
    pass

"""
Note:- keep in mind that our .kv file name was ui.kv so our rendering class(class which will render our application) name
should be like uiApp otherwise we will not get the desired output!!
"""

# this is the main class which will render the whole application
class uiApp(App):

    # method which will render our application
    def build(self):
        return MainWindow()

# running the application
uiApp().run()
```

包含我们的按钮的窗口:

> <mainwindow>:</mainwindow>
> 
> 长方体布局:
> 
> #添加按钮
> 
> 按钮:
> 
> #将出现在按钮上的文本
> 
> 文字:“点击这里打开谷歌搜索”
> 
> 发布时间:
> 
> #导入 web 浏览器模块
> 
> 导入 web 浏览器
> 
> #它会在你的浏览器中打开谷歌窗口
> 
> web browser . open(' http://www . Google . com ')
> 
> 打印(请参见这些脚本现在正在使用 kivy 文件运行)

**输出:**

当你点击按钮时，它将打开谷歌页面，并在终端上打印 ui.kv 文件中定义的打印语句的内容，你可以在给定的视频中看到。

<video class="wp-video-shortcode" id="video-553006-3" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210202200306/output1.mp4?_=3">[https://media.geeksforgeeks.org/wp-content/uploads/20210202200306/output1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210202200306/output1.mp4)</video>