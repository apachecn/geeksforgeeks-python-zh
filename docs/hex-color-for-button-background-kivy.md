# 按钮背景的十六进制颜色–Kivy

> 原文:[https://www . geesforgeks . org/hex-color-for-button-background-kivy/](https://www.geeksforgeeks.org/hex-color-for-button-background-kivy/)

[Kivy](https://www.geeksforgeeks.org/kivy-tutorial/) 是 Python 中独立于平台的 GUI 工具。它可以在安卓、IOS、Linux 和 Windows 等平台上运行。这是 python 中唯一一个可以在安卓设备上独立运行的图形用户界面库，即使我们也可以在树莓 pi 上使用它。它是一个开源的 Python 库，用于快速开发多点触控应用程序。它的图形引擎是建立在 OpenGL 之上的，并且它还支持一个快速的图形管道。

本文重点介绍使用带有按钮的 kivy 创建一个 GUI 窗口，然后使用十六进制颜色代码为其添加颜色。

### 方法

*   导入描述按钮
*   导入鄙视应用
*   Import deska
*   创建应用程序类
*   创建按钮
*   创建点击按钮时改变颜色的机制
*   返回生成器字符串
*   运行类的实例

**程序:**

## 蟒蛇 3

```
# importing button widget from kivy framework
from kivy.uix.button import Button

from kivy.app import App

# importing builder from kivy
from kivy.lang import Builder

# this is the main class which will 
# render the whole application
class uiApp(App):

    # method which will render our application
    def build(self):

        return Builder.load_string("""

#:import C kivy.utils.get_color_from_hex
Button:

   # text which will appear on first button
   text:"first button"

   background_color: C("#f9f871")
                                   """)

# running the application
uiApp().run()
```

**输出:**

<video class="wp-video-shortcode" id="video-553531-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210204124445/hexupdated.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210204124445/hexupdated.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210204124445/hexupdated.mp4)</video>