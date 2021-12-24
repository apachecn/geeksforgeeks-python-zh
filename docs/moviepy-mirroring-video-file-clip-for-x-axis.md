# 电影-镜像 x 轴的视频文件剪辑

> 原文:[https://www . geesforgeks . org/moviepy-镜像-视频-文件-剪辑-用于 x 轴/](https://www.geeksforgeeks.org/moviepy-mirroring-video-file-clip-for-x-axis/)

在本文中，我们将看到如何在 MoviePy 中将视频文件剪辑镜像到 x 轴。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。镜像视频根据 x 轴，镜像视频(在平面镜中)是物体的反射副本，看起来几乎相同，但在垂直于镜面的方向上是相反的。作为一种光学效应，它是由镜子或水等物质的反射产生的。

> 为此，我们将对视频文件剪辑对象使用`fx`方法
> 
> **语法:** clip.fx(vfx.mirror_x)
> 
> **自变量:**它以 vfx 对象为自变量
> 
> **返回:**返回视频文件剪辑对象

下面是实现

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.webm")

# getting subclip from the original video
clip = clip.subclip(0, 10)

# mirroring image according to the x axis
clip = clip.fx(vfx.mirror_x)

# showing final clip
clip.ipython_display()
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-457223-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722094549/121.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200722094549/121.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722094549/121.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip from it
clip1 = clip.subclip(0, 7)

# mirroring image according to the x axis
clip = clip.fx(vfx.mirror_x)

# showing final clip
clip.ipython_display()
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

<video class="wp-video-shortcode" id="video-457223-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722094623/214.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200722094623/214.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722094623/214.mp4)</video>