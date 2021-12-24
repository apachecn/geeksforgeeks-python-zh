# 影片–获取视频文件剪辑的持续时间

> 原文:[https://www . geesforgeks . org/moviepy-get-duration-of-video-file-clip/](https://www.geeksforgeeks.org/moviepy-getting-duration-of-video-file-clip/)

在本文中，我们将了解如何在 MoviePy 中获取视频文件剪辑的持续时间。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。持续时间基本上是视频的长度，即视频有多长，以秒为单位。

> 为此，我们将对视频文件剪辑对象使用`duration`方法
> 
> **语法:**剪辑.持续时间
> 
> **论证:**不需要论证
> 
> **返回:**返回浮动

下面是实现

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# getting duration of the video
duration = clip.duration

# printing duration
print("Duration : " + str(duration))

# showing final clip
clip.ipython_display()
```

**输出:**

```py
Duration : 5
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-460220-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200727005027/132.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200727005027/132.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200727005027/132.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting duration of the video
duration = clip.duration

# printing duration
print("Duration : " + str(duration))

# showing final clip
clip.ipython_display()
```

**输出:**

```py
Duration : 10.98
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-460220-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200727004916/225.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200727004916/225.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200727004916/225.mp4)</video>