# Python |使用 kivy 中的时钟对象创建秒表使用。kv 文件

> 原文:[https://www . geesforgeks . org/python-create-a-秒表-使用-clock-in-object-kivy-using-kv-file/](https://www.geeksforgeeks.org/python-create-a-stopwatch-using-clock-object-in-kivy-using-kv-file/)

Kivy 是 Python 中独立于平台的 GUI 工具。因为它可以在安卓、IOS、Linux 和视窗等平台上运行。它基本上是用来开发安卓应用的，但并不意味着它不能在桌面应用上使用。

> [Kivy 教程–通过示例学习 Kivy](https://www.geeksforgeeks.org/kivy-tutorial/)。

**Clock 对象:**
Clock 对象可以让你安排未来的函数调用；一次或以特定的时间间隔重复。
您可以通过 dt 参数
获得调度和回调调用之间经过的时间

## 蟒蛇 3

```py
# define callback
def my_callback(dt):
    pass

# clock.schedule_interval with time specified
Clock.schedule_interval(my_callback, 0.5)

# clock.schedule_once with time specified
Clock.schedule_once(my_callback, 5)

# call my_callback as soon as possible.
Clock.schedule_once(my_callback)
```

**注意:如果回调返回 False，日程将被取消，不会重复。**

在这里，我们将创建秒表，我们将创建 3 个按钮，分别是开始、暂停、继续。

> 使用 kivy 内置模块时最好使用 kivy.clock 导入 clock 中的 clock 和:

```py
Basic Approach:  
1) import kivy
2) import kivyApp
3) import Builder
4) import Boxlayout
5) Import clock
6) import kivy properties(only needed one)
7) Set minimum version(optional)
8) Create the .kv code:
     1) Create Buttons
     2) Add call to button
     3) Add label 
9) Create Layout class
10) Create App class
11) return Layout/widget/Class(according to requirement)
12) Run an instance of the class
```

**#实施方法:**

## 蟒蛇 3

```py
'''
Code of How to create Stopwatch
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

# The Builder is responsible for creating
# a Parser for parsing a kv file
from kivy.lang import Builder

# The Properties classes are used
# when you create an EventDispatcher.
from kivy.properties import NumericProperty

# BoxLayout arranges children in a vertical or horizontal box.
# or help to put the children at the desired location.
from kivy.uix.boxlayout import BoxLayout

# he Clock object allows you to
# schedule a function call in the future
from kivy.clock import Clock

# Create the .kv file and load it by using Builder
Builder.load_string('''

<MainWidget>:

    # Assigning the alignment to buttons
    BoxLayout:
        orientation: 'vertical'

        # Create Button

        Button:
            text: 'start'
            on_press: root.start()

        Button:
            text: 'stop'
            on_press: root.stop()

        Button:
            text: 'Reset'
            on_press: root.number = 0

    # Create the Label
    Label:
        text: str(round(root.number))
        text_size: self.size
        halign: 'center'
        valign: 'middle'
''')

# Create the Layout class
class MainWidget(BoxLayout):

    number = NumericProperty()

    def __init__(self, **kwargs):

        # The super() builtin
        # returns a proxy object that
        # allows you to refer parent class by 'super'.
        super(MainWidget, self).__init__(**kwargs)

        # Create the clock and increment the time by .1 ie 1 second.
        Clock.schedule_interval(self.increment_time, .1)

        self.increment_time(0)

    # To increase the time / count
    def increment_time(self, interval):
        self.number += .1

    # To start the count
    def start(self):

        Clock.unschedule(self.increment_time)
        Clock.schedule_interval(self.increment_time, .1)

    # To stop the count / time
    def stop(self):
        Clock.unschedule(self.increment_time)

# Create the App class
class TimeApp(App):
    def build(self):
        return MainWidget()

# Run the App
TimeApp().run()
```

**输出:**

<video class="wp-video-shortcode" id="video-346951-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210131141224/FreeOnlineScreenRecorderProject6.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210131141224/FreeOnlineScreenRecorderProject6.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210131141224/FreeOnlineScreenRecorderProject6.mp4)</video>

**注:**

在这种情况下，当您按下开始计数开始时，当按下重新启动时，它会再次启动，当按下暂停时，它会暂停。