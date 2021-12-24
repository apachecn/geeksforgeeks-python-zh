# 影片–更改视频剪辑的时间线

> 原文:[https://www . geesforgeks . org/moviepy-更改时间-视频剪辑行/](https://www.geeksforgeeks.org/moviepy-changing-time-line-of-video-clip/)

在本文中，我们将看到如何在 MoviePy 中更改视频文件剪辑的时间线。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。在视频编辑中，时间轴是大多数视频编辑程序中常用的界面。该界面使作者能够在显示器上以线性方式水平布置视频项目。非线性编辑系统中编辑序列的时间显示。通过改变视频的时间线，我们可以改变视频中事件的顺序。

> 为此，我们将对视频文件剪辑对象使用`fl_time`方法
> 
> **语法:** clip.fl_time(方法)
> 
> **自变量:**以时间方法为自变量
> 
> **返回:**返回视频文件剪辑对象

下面是实现

```py
# Import everything needed to edit video clips
from moviepy.editor import * import math  

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# applying color effect
final = clip.fl_time(lambda t: math.sin(t))

# setting duration
final.duration = 9

# showing final clip
final.ipython_display()
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-460224-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200727001141/130.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200727001141/130.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200727001141/130.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip from it
clip = clip.subclip(0, 5)

# altering time intervalr effect
final = clip.fl_time(lambda t: 2 * t)

# setting duration
final.duration = 10

# showing final clip
final.ipython_display()
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

<video class="wp-video-shortcode" id="video-460224-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200727001204/223.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200727001204/223.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200727001204/223.mp4)</video>