# 电影-创建复合视频剪辑

> 原文:[https://www . geesforgeks . org/moviepy-creating-composite-video-clips/](https://www.geeksforgeeks.org/moviepy-creating-composite-video-clips/)

在本文中，我们将看到如何在 MoviePy 中合成视频文件。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。复合的含义是组合不同的元素，复合视频是不同视频剪辑的组合不同于视频文件的堆叠和拼接复合文件易于实现但结构复杂。复合文件将剪辑组合在一起，同时播放，视频播放的位置和时间可以随时设置。

> 为了做到这一点，我们将使用复合视频剪辑方法
> **语法:**复合视频剪辑(剪辑)
> **参数:**它以视频剪辑列表作为参数
> **返回:**它返回视频文件剪辑对象

下面是实现

## 蟒蛇 3

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video and getting only first 5 seconds
clip1 = VideoFileClip("dsa_geek.webm").subclip(0, 5)

# rotating clip1 by 90 degree to get the clip2
clip2 = clip1.margin(40).set_start(3)

# rotating clip1 by 180 degree to get the clip3
clip3 = clip1.rotate(180).set_start(6)

# creating a composite video
final = CompositeVideoClip([clip2, clip1, clip3])

# showing final clip
final.ipython_display(width = 480)
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-457227-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722101712/123.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200722101712/123.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722101712/123.mp4)</video>

**另一个例子**

## 蟒蛇 3

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip from it
clip1 = clip.subclip(0, 5)

# mirroring image according to the y axis
clip2 = clip.fx(vfx.mirror_y).set_start((4))

# creating a composite video
final = CompositeVideoClip([clip1, clip2])

# showing final clip
final.ipython_display(width = 480)
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.

MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.

Moviepy - Writing video __temp__.mp4

Moviepy - Done !

Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-457227-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722102001/216.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200722102001/216.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722102001/216.mp4)</video>