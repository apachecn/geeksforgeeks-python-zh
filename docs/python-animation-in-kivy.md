# Python | Kivy 中的动画

> 原文:[https://www.geeksforgeeks.org/python-animation-in-kivy/](https://www.geeksforgeeks.org/python-animation-in-kivy/)

Kivy 是 Python 中独立于平台的 GUI 工具。因为它可以在安卓、IOS、Linux 和视窗等平台上运行。它基本上是用来开发安卓应用程序的，但并不意味着它不能在桌面应用程序上使用。

> 👉🏽 [Kivy 教程–通过示例学习 Kivy](https://www.geeksforgeeks.org/kivy-tutorial/)。

## 动画:

动画和动画转换用于动画小部件属性。您必须至少指定一个属性名称和目标值。要使用动画，请按照下列步骤操作:

*   设置动画对象
*   在小部件上使用动画对象

> 要使用动画，您必须从 kivy 导入:
> 动画导入动画

```py
Basic Approaches: 

1) import kivy
2) import kivyApp
3) import Button
4) import Animation
5) set kivy version (optional)
6) Create the App class
7) Define animation
8) Add animations
9) Run the App
```

**实施方法:**

```py
# Widget animation in kivy

# import kivy module 
import kivy 

# this restricts the kivy version i.e 
# below this kivy version you cannot 
# use the app or software 
kivy.require("1.9.1") 

# base Class of your App inherits from the App class. 
# app:always refers to the instance of your application 
from kivy.app import App 

# To work with Animation you must have to import it
from kivy.animation import Animation

# The Button is a Label with associated
# actions that are triggered when the button
# is pressed (or released after a click/touch). 
from kivy.uix.button import Button

# Create the App class
class TestApp(App):

   # Defining the function in which animations are added

    def animate(self, instance):
        # create an animation object. This object could be stored
        # and reused each call or reused across different widgets.
        # += is a sequential step, while &= is in parallel
        animation = Animation(pos =(100, 100), t ='out_bounce')
        animation += Animation(pos =(200, 100), t ='out_bounce')
        animation &= Animation(size =(500, 500))
        animation += Animation(size =(100, 50))

        # apply the animation on the button, passed in the "instance" argument
        # Notice that default 'click' animation (changing the button
        # color while the mouse is down) is unchanged.
        animation.start(instance)

    def build(self):
        # create a button, and  attach animate() 
        # method as a on_press handler
        button = Button(size_hint =(None, None), text ='plop',
                        on_press = self.animate)
        return button

# run the App
if __name__ == '__main__':
    TestApp().run()
```

**输出:**

![](img/e998b20f479cbf74350994c3932f4092.png)

当按钮如图所示，当你点击它时，它会显示不同的动画。

<video class="wp-video-shortcode" id="video-317547-1" width="665" height="374" preload="metadata" controls=""><source type="video/webm" src="https://media.geeksforgeeks.org/wp-content/uploads/20190627161231/Animation.webm?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20190627161231/Animation.webm](https://media.geeksforgeeks.org/wp-content/uploads/20190627161231/Animation.webm)</video>