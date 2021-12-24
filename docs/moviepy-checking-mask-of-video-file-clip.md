# 电影-检查视频文件剪辑的蒙版

> 原文:[https://www . geesforgeks . org/moviepy-checking-mask-of-video-file-clip/](https://www.geeksforgeeks.org/moviepy-checking-mask-of-video-file-clip/)

在本文中，我们将了解如何检查 MoviePy 中的视频文件剪辑是否是蒙版视频。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。IsMask 属性告诉我们，如果给定的视频剪辑是蒙版还是非蒙版，那么蒙版基本上就是用作另一个视频蒙版的那个视频。我们可以借助`set_ismask`方法制作一个视频剪辑作为蒙版。

> 为了做到这一点，我们将使用视频文件剪辑对象的`ismask`属性
> 
> **语法:**clip . ismsk
> 
> **论证:**不需要论证
> 
> **返回:**返回 bool

下面是实现

```py
# Import everything needed to edit video clips 
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.mp4") 

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# checking if clip is mask
value = clip.ismask

# printing value
print("Clip is Mask ", end = " : ")
print(value)

# displaying new clip
clip.ipython_display(width = 420)
```

**输出:**

```py
Clip is Mask  : False
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-476068-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200827002306/1st9.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200827002306/1st9.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200827002306/1st9.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# masking this clip as amsk
clip = clip.set_ismask(True)

# checking if clip is mask
value = clip.ismask

# printing value
print("Clip is Mask ", end = " : ")
print(value)

# displaying new clip
clip.ipython_display()
```

**输出:**

```py
Clip is Mask  : True
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-476068-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200827003921/download2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200827003921/download2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200827003921/download2.mp4)</video>