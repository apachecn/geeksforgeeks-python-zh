# 影片-设置剪辑的结束时间

> 原文:[https://www . geesforgeks . org/moviepy-设置-剪辑结束时间/](https://www.geeksforgeeks.org/moviepy-setting-end-time-of-the-clip/)

在本文中，我们将了解如何在 MoviePy 中设置视频文件剪辑的结束时间。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。我们可以借助`set_duration`方法改变剪辑的时长。虽然通过改变剪辑的结束时间，我们也可以增加或减少持续时间。

> 为此，我们将对视频文件剪辑对象使用`set_end`方法
> 
> **语法:** clip.set_end(n)
> 
> **自变量:**以浮点值为自变量
> 
> **返回:**返回视频文件剪辑对象

下面是实现

```py
# Import everything needed to edit video clips 
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.mp4") 

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# new clip with new end time
new_clip = clip.set_end(3)

# displaying new clip
new_clip.ipython_display(width = 360)
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-475315-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200826030303/1st7.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200826030303/1st7.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200826030303/1st7.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 2 seconds
clip = clip.subclip(0, 2)

# new clip with new end time
new_clip = clip.set_end(3)

# displaying new clip
new_clip.ipython_display(width = 360)
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

<video class="wp-video-shortcode" id="video-475315-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200826030241/2nd6.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200826030241/2nd6.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200826030241/2nd6.mp4)</video>