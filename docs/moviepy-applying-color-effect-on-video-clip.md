# 电影-在视频剪辑上应用颜色效果

> 原文:[https://www . geeksforgeeks . org/moviepy-视频剪辑应用颜色效果/](https://www.geeksforgeeks.org/moviepy-applying-color-effect-on-video-clip/)

在本文中，我们将了解如何在 MoviePy 中对视频文件剪辑应用颜色效果。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。色彩效果用于增加或减少色彩强度，当我们降低强度时，色彩看起来更暗，而通过增加强度，它看起来更亮。

> 为此，我们将对视频文件剪辑对象使用`fx`方法
> 
> **语法:** clip.fx( vfx.colorx，m)
> 
> **自变量:**它以 vfx 对象和乘数为自变量
> 
> **返回:**返回视频文件剪辑对象

下面是实现

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# applying color effect
final = clip.fx( vfx.colorx, 1.5)

# showing final clip
final.ipython_display()
```

**输出:**

```
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-460226-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200726234326/129.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200726234326/129.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200726234326/129.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip from it
clip = clip.subclip(0, 9)

# applying color effect
final = clip.fx( vfx.colorx, 0.5)

# showing final clip
final.ipython_display()
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

<video class="wp-video-shortcode" id="video-460226-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200726234303/222.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200726234303/222.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200726234303/222.mp4)</video>