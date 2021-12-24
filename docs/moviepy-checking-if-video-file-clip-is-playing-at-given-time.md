# 电影–检查视频文件剪辑是否在给定时间播放

> 原文:[https://www . geesforgeks . org/moviepy-检查视频文件剪辑是否在给定时间播放/](https://www.geeksforgeeks.org/moviepy-checking-if-video-file-clip-is-playing-at-given-time/)

在本文中，我们将了解如何检查 MoviePy 中的视频文件剪辑是否会在给定的时间播放。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。这意味着如果视频被播放并且时间 t，视频将会继续播放或者被终止。

> 为此，我们将对视频文件剪辑对象使用`is_playing`方法
> 
> **语法:** clip.is_playing(t)
> 
> **自变量:**以浮点值为自变量
> 
> **返回:**返回 bool

下面是实现

```
# Import everything needed to edit video clips 
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.mp4") 

# getting only first 5 seconds 
clip = clip.subclip(0, 5) 

# checking if clip will be playing at time 2
value = clip.is_playing(2)

# printing the value
print("Clip will be playing at time = 2 ", end =" : ")
print(value)

# showing  clip 
clip.ipython_display(width = 360)
```

**输出:**

```
Clip will be playing at time = 2  : True
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-475297-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200825235530/1st2.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200825235530/1st2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200825235530/1st2.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# checking if clip will be playing at time 8
value = clip.is_playing(8)

# printing the value
print("Clip will be playing at time = 8 ", end =" : ")
print(value)

# showing  clip 
clip.ipython_display(width = 360)
```

**输出:**

```
Clip will be playing at time = 8  : False
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-475297-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200825235546/2nd2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200825235546/2nd2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200825235546/2nd2.mp4)</video>