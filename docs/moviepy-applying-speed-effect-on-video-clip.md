# 电影-对视频剪辑应用速度效果

> 原文:[https://www . geesforgeks . org/moviepy-应用速度-视频剪辑效果/](https://www.geeksforgeeks.org/moviepy-applying-speed-effect-on-video-clip/)

在本文中，我们将了解如何在 MoviePy 中对视频文件剪辑应用速度效果。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。在视频制作中，加速或减速也称为快动作/慢动作效果，它使视频剪辑的播放速度比原始速度更快或更慢。

> 为此，我们将对视频文件剪辑对象使用`fx`方法
> 
> **语法:** clip.fx( vfx.speedx，m)
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

# applying speed effect
final = clip.fx( vfx.speedx, 0.5)

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

<video class="wp-video-shortcode" id="video-460228-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200726233742/128.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200726233742/128.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200726233742/128.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip from it
clip = clip.subclip(0, 9)

# applying speed effect
final = clip.fx( vfx.speedx, 2)

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

<video class="wp-video-shortcode" id="video-460228-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200726233802/221.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200726233802/221.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200726233802/221.mp4)</video>