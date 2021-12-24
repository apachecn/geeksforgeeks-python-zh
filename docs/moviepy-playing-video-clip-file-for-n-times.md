# 电影-播放视频剪辑文件 n 次

> 原文:[https://www . geesforgeks . org/moviepy-playing-video-clip-file-for-n-times/](https://www.geeksforgeeks.org/moviepy-playing-video-clip-file-for-n-times/)

在本文中，我们将看到如何循环播放视频文件剪辑，即在 MoviePy 中播放 n 次。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。我们可以借助`ipython_display`方法显示视频，也可以借助`preview`方法预览视频。但是当我们显示一个视频时，没有循环，尽管我们可以随时添加循环，即当我们显示视频文件时，它将开始播放自己 n 次。

> 为此，我们将对视频文件剪辑对象使用`ipython_display`方法
> 
> **语法:**clip . clip . ipython _ display(loop = n)
> 
> **自变量:**以 loop = integer 为自变量
> 
> **返回:**返回无

下面是实现

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# looping video 3 times
clip.ipython_display(loop = 3)
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-462995-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200730192857/136.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200730192857/136.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200730192857/136.mp4)</video>
This video will get played 3 times in continuous loop

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# looping video 3 times
clip.ipython_display(loop = 3)
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

<video class="wp-video-shortcode" id="video-462995-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200730192952/230.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200730192952/230.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200730192952/230.mp4)</video>
This video will get played 3 times in continuous loop