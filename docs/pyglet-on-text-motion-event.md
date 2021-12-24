# PYGLET–文本运动事件

> 原文:[https://www.geeksforgeeks.org/pyglet-on-text-motion-event/](https://www.geeksforgeeks.org/pyglet-on-text-motion-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发文本运动事件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。通常，这是在 on_key_press()之后和 on_key_release()之前调用的，但是如果该键被按下(键重复)，也可能被调用多次。我们应该总是使用这个方法来移动文本输入光标(脱字符号)，因为不同的平台有不同的默认键盘映射，并且键重复被正确处理。

我们可以在下面命令的帮助下创建一个窗口

```py
pyglet.window.Window(width, height, title)

```

下面是 on text motion 的语法，当触发此事件时会调用此方法

```py
@window.event       
def on_text_motion(motion):
    print("Arrow Key pressed")

```

> 以下是本次活动涵盖的议案列表
> 
> MOTION _ UP
> MOTION _ RIGHT
> MOTION _ DOWN
> MOTION _ LEFT
> MOTION _ NEXT _ WORD
> MOTION _ PREVIOUS _ WORD
> MOTION _ start _ OF _ LINE
> MOTION _ END _ OF _ LINE
> MOTION _ NEXT _ PAGE
> MOTION _ PREVIOUS _ PAGE
> MOTION _ start _ OF _ FILE
> MOTION _ END _ OF _ FILE
> MOTION _ back space
> MOTION _ DELETE

下面是实现

```py
# importing pyglet module
import pyglet
import pyglet.window.key

# width of window
width = 500

# height of window
height = 500

# caption i.e title of the window
title = "Geeksforgeeks"

# creating a window
window = pyglet.window.Window(width, height, title)

# text 
text = "GeeksforGeeks"

# creating a label with font = times roman
# font size = 36
# aligning it to the centre
label = pyglet.text.Label(text,
                          font_name ='Times New Roman',
                          font_size = 36,
                          x = window.width//2, y = window.height//2,
                          anchor_x ='center', anchor_y ='center')

new_label = pyglet.text.Label(text,
                          font_name ='Times New Roman',
                          font_size = 10,
                          x = 25, y = 25)

# on draw event
@window.event
def on_draw():    

    # clearing the window
    window.clear()

    # drawing the label on the window
    label.draw()

# key press event    
@window.event
def on_key_press(symbol, modifier):

    # key "C" get press
    if symbol == pyglet.window.key.C:

        print("Key C is pressed")

# on text motion event
@window.event
def on_text_motion(motion):

    # prinitng message
    print(motion)

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**
![](img/9e4ae5db65098e675641e54c86d51ad9.png)

当我们按下箭头键时，这条信息将被打印出来

```py
65362
65362
65362
65363
65363
65363
65361
65361
65361
65364

```