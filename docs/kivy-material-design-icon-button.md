# Kivy–材料设计图标按钮

> 原文:[https://www . geesforgeks . org/kivy-material-design-icon-button/](https://www.geeksforgeeks.org/kivy-material-design-icon-button/)

[Kivy](https://www.geeksforgeeks.org/kivy-tutorial/) 是 Python 中独立于平台的 GUI 工具。它可以在安卓、IOS、Linux 和 Windows 等平台上运行。这是 python 中唯一一个可以在安卓设备上独立运行的图形用户界面库，即使我们也可以在树莓 pi 上使用它。这是一个开源的 Python 库，用于快速开发利用创新用户界面的应用程序，例如多点触控应用程序。它的图形引擎建立在 OpenGL ES 2 之上，并具有快速的图形流水线。

在本文中，我们将使用 python 的 kivy 框架开发一个 GUI 窗口，我们将在这个窗口上添加不同大小的材质设计图标按钮。

**进场:**

*   导入所需模块。
*   创建应用程序类。
*   添加按钮。
*   返回布局。
*   运行类的实例。

**实施:**

## 蟒蛇 3

```py
# importing mdapp from kivymd framework
from kivymd.app import MDApp

# importing builder from kivy
from kivy.lang import Builder

# this is the main class which
# will render the whole application
class uiApp(MDApp):

    # method which will render our application
    def build(self):
        return Builder.load_string("""

MDBoxLayout:
    spacing:300
    MDIconButton:

        # name of mdicon
        icon:"language-python"                          
        pos_hint: {"center_x": .5, "center_y": .5}
        user_font_size: "64sp"

        # bgcolor of iconbutton
        md_bg_color:[1,1,0,1]                           

    MDIconButton:

        # custom image as mdicon
        icon:"gfg.png"                                  
        pos_hint: {"center_x": .5, "center_y": .5}
        user_font_size: "16sp"

    MDIconButton:

        icon:"language-python"
        pos_hint: {"center_x": .5, "center_y": .5}

                                   """)

# running the application
uiApp().run()
```

**输出:**

<video class="wp-video-shortcode" id="video-557265-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210211225711/iconbutton.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210211225711/iconbutton.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210211225711/iconbutton.mp4)</video>