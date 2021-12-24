# 电影-保存一帧视频剪辑

> 原文:[https://www . geesforgeks . org/moviepy-保存一帧视频剪辑/](https://www.geeksforgeeks.org/moviepy-saving-a-frame-of-video-clip/)

在本文中，我们将了解如何在给定时间在 MoviePy 中保存视频文件剪辑的单帧。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。我们可以随时存储特定的帧。

> 为此，我们将对视频文件剪辑对象使用`save_frame`方法
> 
> **语法:**clip . save _ frame(“frame . png”，t)
> 
> **参数:**以图像名称为参数，时间为可选参数
> 
> **返回:**返回无

下面是实现

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# saving a frame at 2 second
clip.save_frame("frame2.png", t = 2)

# showing  clip
clip.ipython_display(width = 360)
```

**输出:**

```
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-462408-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200730174104/134.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200730174104/134.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200730174104/134.mp4)</video>

下面是保存的图片
![](img/30f1ea42191fa0aa7996dc92d03a34b7.png)

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting duration of the video
duration = clip.duration

# saving a frame at 1 second
clip.save_frame("frame1.png", t = 1)

# showing  clip
clip.ipython_display(width = 360)
```

**输出:**

```
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-462408-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200730174035/228.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200730174035/228.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200730174035/228.mp4)</video>

下面是保存的图像看起来如何
![](img/2d6dbf30eca6fdd1cfd5513c260b5959.png)