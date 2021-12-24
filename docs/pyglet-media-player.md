# PYGLET–媒体播放器

> 原文:[https://www.geeksforgeeks.org/pyglet-media-player/](https://www.geeksforgeeks.org/pyglet-media-player/)

在本文中，我们将看到如何在 python 的 PYGLET 模块中创建一个简单的媒体播放器。Pyglet 是一个易于使用但功能强大的库，用于开发视觉上丰富的图形用户界面应用程序，如游戏、多媒体等。窗口是占用操作系统资源的“重量级”对象。窗口可能显示为浮动区域，或者可以设置为充满整个屏幕(全屏)。为了加载一个文件即资源，我们使用 pyglet 的资源模块。该模块允许应用程序指定资源的搜索路径。Pyglet 可以播放 WAV 文件，如果安装了 FFmpeg，还可以播放许多其他音频和视频格式。播放由 Player 类处理，该类从 Source 对象读取原始数据，并提供暂停、查找、调整音量等方法。播放器类实现了最好的音频设备。
我们可以借助下面给出的命令
来创建一个窗口和玩家对象

```py
# creating a window
window = pyglet.window.Window(width, height, title)

# creating a player for media
player = pyglet.media.Player()
```

> 为了在 pyglet 中播放媒体，我们必须执行以下操作
> 1。创建 pyglet 窗口
> 2。创建玩家对象
> 3。从媒体路径
> 4 按播放器加载媒体。将加载的媒体添加到播放器
> 5 的队列中。播放视频
> 6。创建用于暂停和恢复视频的按键事件处理程序

下面是实现

## 蟒蛇 3

```py
# importing pyglet module
import pyglet

# width of window
width = 500

# height of window
height = 500

# caption i.e title of the window
title = "Geeksforgeeks"

# creating a window
window = pyglet.window.Window(width, height, title)

# video path
vidPath ="media.mp4"

# creating a media player object
player = pyglet.media.Player()

# creating a source object
source = pyglet.media.StreamingSource()

# load the media from the source
MediaLoad = pyglet.media.load(vidPath)

# add this media in the queue
player.queue(MediaLoad)

# play the video
player.play()

# on draw event
@window.event
def on_draw():

    # clea the window
    window.clear()

    # if player source exist
    # and video format exist
    if player.source and player.source.video_format:

        # get the texture of video and
        # make surface to display on the screen
        player.get_texture().blit(0, 0)

# key press event    
@window.event
def on_key_press(symbol, modifier):

    # key "p" get press
    if symbol == pyglet.window.key.P:

        # printing the message
        print("Key : P is pressed")

        # pause the video
        player.pause()

        # printing message
        print("Video is paused")

    # key "r" get press
    if symbol == pyglet.window.key.R:

        # printing the message
        print("Key : R is pressed")

        # resume the video
        player.play()

        # printing message
        print("Video is resumed")

# run the pyglet application
pyglet.app.run()
```

**输出:**

<video class="wp-video-shortcode" id="video-486301-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200915002720/Geeksforgeeks-2020-09-15-00-26-54.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200915002720/Geeksforgeeks-2020-09-15-00-26-54.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200915002720/Geeksforgeeks-2020-09-15-00-26-54.mp4)</video>

```py
Key : P is pressed
Video is paused
Key : R is pressed
Video is resumed
Key : P is pressed
Video is paused
Key : R is pressed
Video is resumed
```