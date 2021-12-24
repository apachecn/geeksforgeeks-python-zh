# 电影-在视频剪辑的同时改变图像和时间

> 原文:[https://www . geesforgeks . org/moviepy-视频剪辑同时更改图像和时间/](https://www.geeksforgeeks.org/moviepy-changing-image-and-time-at-same-time-of-video-clip/)

在本文中，我们将看到如何在 MoviePy 中同时更改视频文件剪辑的显示帧和时间线。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。我们用`fl_image`方法改变显示帧，`fl_time`方法改变时间，虽然我们可以同时做这些任务。

> 为此，我们将对视频文件剪辑对象使用`fl`方法
> 
> **语法:** clip.fl(方法)
> 
> **自变量:**以时间方法为自变量
> 
> **返回:**返回视频文件剪辑对象

下面是实现

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

def scroll(get_frame, t):
    """
    This function returns a 'region' of the current frame.
    The position of this region depends on the time.
    """
    frame = get_frame(t)
    frame_region = frame[int(t):int(t)+360, :]
    return frame_region

# alter time and frame
final = clip.fl( scroll )

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

<video class="wp-video-shortcode" id="video-460218-1" width="665" height="280" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200727012359/133.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200727012359/133.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200727012359/133.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting duration of the video
duration = clip.duration

def scroll(get_frame, t):
    """
    This function returns a 'region' of the current frame.
    The position of this region depends on the time.
    """
    frame = get_frame(t)
    frame_region = frame[int(t):int(t)+360, :]
    return frame_region

# alter time and frame
final = clip.fl( scroll )

# showing final clip
final.ipython_display()
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

<video class="wp-video-shortcode" id="video-460218-2" width="656" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200727012412/227.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200727012412/227.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200727012412/227.mp4)</video>