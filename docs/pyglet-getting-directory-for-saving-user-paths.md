# PYGLET–获取保存用户路径的目录

> 原文:[https://www . geeksforgeeks . org/pyglet-get-directory-for-saving-user-path/](https://www.geeksforgeeks.org/pyglet-getting-directory-for-saving-user-paths/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中获取保存用户路径的目录。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。为了加载一个文件即资源，我们使用 pyglet 的资源模块。该模块允许应用程序指定资源的搜索路径。相对路径被认为是相对于应用程序的 __main__ 模块的。不同的平台有不同的惯例来保存用户偏好、保存的游戏和设置。这个函数实现了那些约定。请注意，返回的路径可能不存在:如果需要，应用程序应该使用 os.makedirs 来构造它。在 Linux 上，返回用户配置目录中的目录名(通常在~/)下。配置)。在 Windows 上(包括 Cygwin 下)，将返回用户应用程序设置目录中的名称目录。
我们可以借助下面给出的命令
创建一个窗口对象

```py
# creating a window
window = pyglet.window.Window(width, height, title)
```

> 为此，我们将 get_settings_path 方法与 pyglet.resource
> **一起使用语法:**resource . get _ settings _ path(name)
> **参数:**它将字符串作为参数
> **返回:**它返回字符串

**示例:**下面是实现

## 蟒蛇 3

```py
#importing pyglet module
import pyglet
import pyglet.window.key as key

# width of window
width = 500

# height of window
height = 500

# caption i.e title of the window
title = "Geeksforgeeks"

# creating a window
window = pyglet.window.Window(width, height, title)

# text 
text = "Welcome to GeeksforGeeks"

# creating label with following properties
# font = cooper
# position = 250, 150
# anchor position = center
label = pyglet.text.Label(text,
                          font_name ='Cooper',
                          font_size = 16,
                          x = 250, 
                          y = 150,
                          anchor_x ='center', 
                          anchor_y ='center')

# creating a batch
batch = pyglet.graphics.Batch()

# loading geeksforgeeks image
image = pyglet.image.load('gfg.png')

# creating sprite object
# it is instance of an image displayed on-screen
sprite = pyglet.sprite.Sprite(image, x = 200, y = 230)

# on draw event
@window.event
def on_draw():

    # clear the window
    window.clear()

    # draw the label
    label.draw()

    # draw the image on screen
    sprite.draw()

# key press event    
@window.event
def on_key_press(symbol, modifier):

    # key "C" get press
    if symbol == key.C:

        # printing the message
        print("Key : C is pressed")

# image for icon
img = image = pyglet.resource.image("gfg.png")

# setting image as icon
window.set_icon(img)

# getting directory setting path
value = pyglet.resource.get_settings_path("Application Settings")

# setting text  of label
label.text = str(value)

# start running the application
pyglet.app.run()
```

**输出:**

![](img/0f06d501462e3d57792c1b6334fd652e.png)