# Python–在 kivy

中的任何小部件上添加双击

> 原文:[https://www . geeksforgeeks . org/python-添加-双击任何小部件-in-kivy/](https://www.geeksforgeeks.org/python-adding-double-tap-on-any-widget-in-kivy/)

Kivy 是 Python 中独立于平台的 GUI 工具。它可以在安卓、IOS、Linux 和 Windows 等平台上运行。这是 python 中唯一一个可以在安卓设备上独立运行的图形用户界面库，即使我们也可以在树莓皮上使用它。这是一个开源的 Python 库，用于快速开发利用创新用户界面的应用程序，例如多点触控应用程序。它的图形引擎建立在 OpenGL ES 2 之上，并具有快速的图形流水线。如果你是新手，你可以从这个[链接](https://www.geeksforgeeks.org/kivy-tutorial/)中学习。

在本文中，我们将使用 python 的 kivy 框架开发一个 GUI 窗口，并且我们将在这个窗口上添加一个图像(您也可以按照相同的模式在其他小部件上实现双击事件)，并且我们将在这个图像上添加双击事件。

#### 实现双击图像小部件的基本方法

1.  从 kivy 包导入图像小部件
2.  从 kivy 包导入触摸行为
3.  导入鄙视应用
4.  从 kivy 包导入 boxlayout
5.  添加小部件
6.  扩展课程
7.  返回布局
8.  运行类的实例

**代码:**

## 蟒蛇 3

```
# importing image widget of kivy framework
from kivy.uix.image import Image

# importing Touch behaviour event from kivy framework
from kivymd.uix.behaviors import TouchBehavior
from kivy.app import App

# importing boxlayout for our application
from kivy.uix.boxlayout import BoxLayout

# attaching touch behaviour with image widget
class ImageWithDoubleTouch(Image, TouchBehavior):

    # event for double-tap
    def on_double_tap(self, instance, *args):
        print("wow!! you have double clicked an image named "+self.source)

# this will connect MainWindow which we have 
# created in ui.kv with main.py file
class MainWindow(BoxLayout):
    pass
"""
Note:- keep in mind that our .kv file name was ui.kv so our rendering 
class(class which will render our application) name 
should be like uiApp otherwise we will not get the desired output!!
"""

# this is the main class which will render 
# the whole application
class uiApp(App):

    # method which will render our application
    def build(self):
        return MainWindow()

# running the application
uiApp().run()
```

#### 描述代码：

> #包含我们图像的窗口
> 
> <mainwindow>:</mainwindow>
> 
> 长方体布局:
> 
> #添加我们在 main.py 文件中创建的 ImageWithDoubleTouch 小部件
> 
> 带双箭头的图像 um bruch:
> 
> #添加图像文件的路径
> 
> 资料来源:gfg.png

**输出:**

<video class="wp-video-shortcode" id="video-552449-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210202203356/doubletap.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210202203356/doubletap.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210202203356/doubletap.mp4)</video>