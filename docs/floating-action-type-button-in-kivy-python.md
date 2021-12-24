# kivy–Python 中的浮动动作类型按钮

> 原文:[https://www . geesforgeks . org/floating-action-type-button-in-kivy-python/](https://www.geeksforgeeks.org/floating-action-type-button-in-kivy-python/)

Kivy 是 Python 中独立于平台的 GUI 工具。因为它可以在安卓、IOS、linux 和 Windows 等平台上运行。它基本上是用来开发安卓应用程序的，但并不意味着它不能在桌面应用程序上使用。
现在在本文中，我们将学习如何使用 kivy python 创建类似于浮动动作按钮的按钮类型。

> **什么是浮动动作按钮？？**
> 浮动动作按钮(FAB)在屏幕上执行主要或最常见的动作。它出现在所有屏幕内容的前面，通常是一个中心带有图标的圆形。

要学习如何创建它，你必须对布局、按钮、画布和画布中的椭圆有很好的了解。这些都是我们要用来创建按钮的。因此，我们正在创建一个按钮，就像我们在 gmail 右侧看到的按钮一样，即用于在移动应用程序(而不是网站)标志中编写新的电子邮件。

![](img/14e2e353564d9593b7d9f8e93d6d6f8e.png)

```
Basic Approach:

1) import kivy
2) import kivyApp
3) import Boxlayout
4) Set minimum version(optional)
5) create Layout class
6) create App class
7) Set up .kv file :
       1) Add Floating Button Properties
       2) Create Main Window
       3) Add Float Button
8) return Layout/widget/Class(according to requirement)
9) Run an instance of the class
```

> [**Kivy 教程——用例子学习 Kivy。**T3】](https://www.geeksforgeeks.org/kivy-tutorial/)

**实施该方法–**
**main . py**

## 蟒蛇 3

```
## Sample Python application demonstrating that
## How to create a button like floating Action Button
## in Kivy using .kv file

###################################################
# import modules

import kivy

# base Class of your App inherits from the App class.  
# app:always refers to the instance of your application 
from kivy.app import App

# BoxLayout arranges widgets in either
# in a vertical fashion that
# is one on top of another or in a horizontal
# fashion that is one after another.
from kivy.uix.boxlayout import BoxLayout

# To change the kivy default settings 
# we use this module config 
from kivy.config import Config 

# 0 being off 1 being on as in true / false 
# you can use 0 or 1 && True or False 
Config.set('graphics', 'resizable', True)

# creating the root widget used in .kv file
class MainWindow(BoxLayout):
    pass

# creating the App class in which name
#.kv file is to be named main.kv
class MainApp(App):
    # defining build()
    def build(self):
        # returning the instance of root class
        return MainWindow()

# run the app
if __name__ == '__main__':
    MainApp().run()
```

**。千伏文件执行**
**主.千伏**

## 蟒蛇 3

```
#.kv file implementation of Float Button

# using Float Layout for the creation of Floatbutton
# Here we are creating the properties of button
# Button will be created in Main window Box Layout

<FloatButton@FloatLayout>
    id: float_root  # Giving id to button
    size_hint: (None, None)
    text: ''
    btn_size: (70, 70)
    size: (70, 70)
    bg_color: (0.404, 0.227, 0.718, 1.0)
    pos_hint: {'x': .6}

    # Adding shape and all, size, position to button
    Button:
        text: float_root.text
        markup: True
        font_size: 40
        size_hint: (None, None)
        size: float_root.btn_size
        pos_hint: {'x': 5.5, 'y': 3.8}
        background_normal: ''
        background_color: (0, 0, 0, 0)
        canvas.before:
            Color:
                rgba: (0.404, 0.227, 0.718, 1.0)
            Ellipse:
                size: self.size
                pos: self.pos

# Creation of main window
<MainWindow>:
    BoxLayout:

        # Creating the Float button
        FloatButton:
            text: '+'
            markup: True
            background_color: 1, 0, 1, 0

```

**输出:**

![](img/12182295e09df5b3948c97e97fc5ea73.png)

![](img/dd9c4a817b1a77f6287d7a2d218260cb.png)