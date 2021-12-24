# PYGLET–鼠标拖动事件

> 原文:[https://www.geeksforgeeks.org/pyglet-on-mouse-drag-event/](https://www.geeksforgeeks.org/pyglet-on-mouse-drag-event/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中触发鼠标拖动事件。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。按下一个或多个鼠标按钮后，鼠标被移动。只要持续按住拖动按钮，即使鼠标离开窗口，该事件也会继续触发。
我们可以借助下面给出的命令创建一个窗口

```py
pyglet.window.Window(width, height, title)
```

下面是鼠标拖动事件的语法，当这个事件被触发时，这个方法被调用

```py
@window.event       
def on_mouse_drag(x, y, dx, dy, buttons, modifiers):
    print("Mouse is dragged")
```

下面是实现

## 蟒蛇 3

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

# on mouse drag event
@window.event
def on_mouse_drag(x, y, dx, dy, buttons, modifiers):

    # printing some message
    print("Mouse is dragged")

# image for icon
img = image = pyglet.resource.image("logo.png")

# setting image as icon
window.set_icon(img)

# start running the application
pyglet.app.run()
```

**输出:**

<video class="wp-video-shortcode" id="video-481539-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200906041244/Geeksforgeeks-2020-09-06-04-12-23.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200906041244/Geeksforgeeks-2020-09-06-04-12-23.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200906041244/Geeksforgeeks-2020-09-06-04-12-23.mp4)</video>

```py
Mouse is dragged
Mouse is dragged
Mouse is dragged
Mouse is dragged
Mouse is dragged
Mouse is dragged
Mouse is dragged
Mouse is dragged
Mouse is dragged
Mouse is dragged
Mouse is dragged
Mouse is dragged
Mouse is dragged
Mouse is dragged
```