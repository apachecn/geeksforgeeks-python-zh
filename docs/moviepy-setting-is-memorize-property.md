# 移动-设置为记忆属性

> 原文:[https://www . geesforgeks . org/moviepy-setting-is-memory-property/](https://www.geeksforgeeks.org/moviepy-setting-is-memorize-property/)

在本文中，我们将看到如何在 MoviePy 中设置视频文件剪辑的 memorize 属性。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。一个视频是多个帧的组合，因此每次都有一个特定的帧。memory 属性告诉剪辑是否应该保留在内存中读取的最后一帧。

> 为此，我们将对视频文件剪辑对象使用`set_memoize`方法
> 
> **语法:** clip.set_memoize(真)
> 
> **自变量:**它以布尔为自变量
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

# setting memorize property
new_clip = clip.set_memoize(True)

# displaying new clip
new_clip.ipython_display(width = 420)
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-476072-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200827002306/1st9.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200827002306/1st9.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200827002306/1st9.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# setting memorize property
new_clip = clip.set_memoize(True)

# displaying new clip
new_clip.ipython_display(width = 420)
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

<video class="wp-video-shortcode" id="video-476072-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200827002455/2nd8.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200827002455/2nd8.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200827002455/2nd8.mp4)</video>