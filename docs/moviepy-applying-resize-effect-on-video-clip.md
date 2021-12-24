# 电影-对视频剪辑应用调整大小效果

> 原文:[https://www . geesforgeks . org/moviepy-appling-resize-effect-on-video-clip/](https://www.geeksforgeeks.org/moviepy-applying-resize-effect-on-video-clip/)

在本文中，我们将了解如何在 MoviePy 中对视频文件剪辑应用调整大小效果。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。我们可以借助`resize`方法调整视频的大小来调整视频剪辑的大小，调整大小滤镜是应用在上面的滤镜类型。

> 为此，我们将对视频文件剪辑对象使用`fx`方法
> 
> **语法:** clip.fx( vfx.resize，width= 280)
> 
> **参数:**它以 vfx 对象和宽度或高度作为可选参数
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

# applying resize filter
final = clip.fx( vfx.resize, width = 280)

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

<video class="wp-video-shortcode" id="video-460216-1" width="280" height="157" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200726233217/127.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200726233217/127.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200726233217/127.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip from it
clip = clip.subclip(0, 5)

# applying resize filter
final = clip.fx( vfx.resize, width = 280)

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

<video class="wp-video-shortcode" id="video-460216-2" width="280" height="172" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200726233154/220.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200726233154/220.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200726233154/220.mp4)</video>