# 电影-播放视频文件剪辑

> 原文:[https://www . geesforgeks . org/moviepy-showing-video-file-clip/](https://www.geeksforgeeks.org/moviepy-showing-video-file-clip/)

在本文中，我们将了解如何在 MoviePy 中显示视频文件剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。将一系列图像组合成一幅运动图像的视觉多媒体源。视频将信号传输到屏幕，并处理屏幕截图的显示顺序。视频通常具有与屏幕上显示的图片相对应的音频成分。

> 为此，我们将对视频文件剪辑对象使用`ipython_display`方法
> 
> **语法:** clip.ipython_display(宽度、高度)
> 
> **参数:**需要两个可选参数，即整数
> 
> **返回:**返回 HTML2 对象

**注意:**视频长度不要太大，否则会产生内存错误，因此要注意这个错误，从原始视频中剪辑一小部分视频。

下面是实现

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting subclip as video is large
clip = clip.subclip(0, 10)

# showing clip
clip.ipython_display(width = 280, height = 320)
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-456654-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200721100902/111.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200721100902/111.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200721100902/111.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# showing clip
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

<video class="wp-video-shortcode" id="video-456654-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200721100953/24.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200721100953/24.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200721100953/24.mp4)</video>