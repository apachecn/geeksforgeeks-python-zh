# Python |在 kivy 中使用时钟对象创建秒表

> 原文:[https://www . geeksforgeeks . org/python-创建秒表-使用 kivy 中的时钟对象/](https://www.geeksforgeeks.org/python-create-a-stopwatch-using-clock-object-in-kivy/)

Kivy 是 Python 中独立于平台的 GUI 工具。因为它可以在安卓、IOS、Linux 和视窗等平台上运行。它基本上是用来开发安卓应用的，但并不意味着它不能在桌面应用上使用。
在本文中，我们将了解如何使用标签创建秒表。
在代码中，我们将使用标签创建一个计数器，当您以秒为单位设置时间时，它将像倒计时一样开始减少，在第二秒钟，我们将使用时钟对象来做同样的事情。

> [Kivy 教程–通过示例学习 Kivy](https://www.geeksforgeeks.org/kivy-tutorial/)。

**时钟对象:**

1.  Kivy 提供时钟对象。
2.  当指定的时间周期过去后，时钟对象可以调用一个函数。
3.  Kivy 中的一个时钟对象可以被配置为在每次持续时间过去时调用一个函数，或者只调用一次。

> 使用 kivy 内置模块，从 kivy.clock 导入 Clock 使用 clock:
> **就好了**

```py
Basic Approach:
1) import kivy
2) import kivyApp
3) import label
4) import Animation
5) Import clock
6) import kivy properties(only needed one)
7) Set minimum version(optional)
8) Create Label class
9) Create App class
10) return Layout/widget/Class(according to requirement)
11) Run an instance of the class
```

**#简单方法:**

## 蟒蛇 3

```py
'''
Code of How to create countdown using label only
'''

# Program to Show how to create a switch
# import kivy module   
import kivy 

# base Class of your App inherits from the App class.   
# app:always refers to the instance of your application  
from kivy.app import App

# this restrict the kivy version i.e 
# below this kivy version you cannot 
# use the app or software 
kivy.require('1.9.0')

# The Label widget is for rendering text.
from kivy.uix.label import Label

# Animation is used to animate Widget properties
from kivy.animation import Animation

# The Properties classes are used when you create an EventDispatcher.
from kivy.properties import StringProperty, NumericProperty

# create a label class
class Clock(Label):

    # Set the numeric property
    # i.e set the counter number you can change it accordingly
    a = NumericProperty(100)  # seconds

    # To start countdown
    def start(self):
        Animation.cancel_all(self)  # stop any current animations
        self.anim = Animation(a = 0, duration = self.a)

        # TO finish count down
        def finish_callback(animation, clock):
            clock.text = "FINISHED"

        self.anim.bind(on_complete = finish_callback)
        self.anim.start(self)

    # If u remove this there will be nothing on screen
    def on_a(self, instance, value):
        self.text = str(round(value, 1))

# Create the App class
class TimeApp(App):
    def build(self):
        # Create the object of Clock class
        clock = Clock()

        # call the function from class Clock
        clock.start()
        return clock

# Run the App
if __name__ == "__main__":
    TimeApp().run()
```

**输出:**

<video class="wp-video-shortcode" id="video-346953-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210131141719/FreeOnlineScreenRecorderProject7.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210131141719/FreeOnlineScreenRecorderProject7.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210131141719/FreeOnlineScreenRecorderProject7.mp4)</video>

**注:**倒计时从 100 开始，0 结束

**#现在使用时钟对象:**

## 蟒蛇 3

```py
'''
Code of How to create countdown using label only
'''

# Program to Show how to create a switch
# import kivy module   
import kivy 

# base Class of your App inherits from the App class.   
# app:always refers to the instance of your application  
from kivy.app import App

# this restrict the kivy version i.e 
# below this kivy version you cannot 
# use the app or software 
kivy.require('1.9.0')

# The Label widget is for rendering text.
from kivy.uix.label import Label

# The Clock object allows you to schedule
# a function call in the future; once or
# repeatedly at specified intervals.
from kivy.clock import Clock

# The kivy App that extends from the App class
class ClockDemo(App):

    count = 0

    def build(self):
       self.myLabel = Label(text ='Waiting for updates...')

       # Start the clock
       Clock.schedule_interval(self.Callback_Clock, 1)

       return self.myLabel

    def Callback_Clock(self, dt):
        self.count = self.count + 1
        self.myLabel.text = "Updated % d...times"% self.count

# Run the app
if __name__ == '__main__':
    ClockDemo().run()
```

**输出:**

<video class="wp-video-shortcode" id="video-346953-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210131141721/FreeOnlineScreenRecorderProject8.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20210131141721/FreeOnlineScreenRecorderProject8.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210131141721/FreeOnlineScreenRecorderProject8.mp4)</video>

**注意:**从 0 开始，一直运行到你切窗