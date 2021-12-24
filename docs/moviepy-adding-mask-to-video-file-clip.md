# 电影-给视频文件剪辑添加蒙版

> 原文:[https://www . geesforgeks . org/moviepy-添加蒙版到视频文件-剪辑/](https://www.geeksforgeeks.org/moviepy-adding-mask-to-video-file-clip/)

在本文中，我们将看到如何在 MoviePy 中为视频文件剪辑添加蒙版。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。IsMask 属性告诉我们，如果给定的视频剪辑是蒙版还是非蒙版，那么蒙版基本上就是用作另一个视频的蒙版的那个视频。我们可以借助`set_ismask`方法制作一个视频剪辑作为蒙版。添加蒙版会给剪辑拷贝一个完全不透明的蒙版(由蒙版组成)。这使得计算比无掩码慢，但在许多情况下很有用。

> 为此，我们将对视频文件剪辑对象使用`add_mask`方法
> 
> **语法:** clip.add_mask()
> 
> **论证:**不需要论证
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

# add mask to the clip
clip = clip.add_mask()

# displaying new clip
clip.ipython_display(width = 420)
```

**输出:**

```
Clip is Mask  : False
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-476066-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200827004432/1st10.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200827004432/1st10.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200827004432/1st10.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# add mask to the clip
clip = clip.add_mask()

# displaying new clip
clip.ipython_display(width = 420)
```

**输出:**

```
Clip is Mask  : True
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-476066-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200827004409/2nd9.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200827004409/2nd9.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200827004409/2nd9.mp4)</video>