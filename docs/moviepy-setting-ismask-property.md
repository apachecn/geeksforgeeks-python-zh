# 移动-设置为任务属性

> 原文:[https://www . geesforgeks . org/moviepy-setting-ismask-property/](https://www.geeksforgeeks.org/moviepy-setting-ismask-property/)

在本文中，我们将看到如何在 MoviePy 中设置视频文件剪辑的 isMask 属性。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。IsMask 属性告诉我们，如果给定的视频剪辑是蒙版还是非蒙版，那么蒙版基本上就是用作另一个视频的蒙版的那个视频。

> 为此，我们将对视频文件剪辑对象使用`set_ismask`方法
> 
> **语法:** clip.set_ismask(真)
> 
> **自变量:**它以布尔为自变量
> 
> **返回:**返回视频文件剪辑对象

下面是实现

```
# Import everything needed to edit video clips 
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.mp4") 

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# marking this video as mask
new_clip = clip.set_ismask(True)

# displaying new clip
new_clip.ipython_display()
```

**输出:**

```
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

![](img/0de186dab3bb375436222f3fabf0bffd.png)
另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# marking this video as mask
new_clip = clip.set_ismask(True)

# displaying new clip
new_clip.ipython_display()
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

<video class="wp-video-shortcode" id="video-476074-1" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200827001806/download-2.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200827001806/download-2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200827001806/download-2.mp4)</video>