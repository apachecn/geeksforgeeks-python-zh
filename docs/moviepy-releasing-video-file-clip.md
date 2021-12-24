# 电影-发布视频文件剪辑

> 原文:[https://www . geesforgeks . org/moviepy-releasing-video-file-clip/](https://www.geeksforgeeks.org/moviepy-releasing-video-file-clip/)

在本文中，我们将了解如何在 MoviePy 中发布视频文件剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。释放视频文件剪辑意味着释放/关闭给定视频文件剪辑使用的所有资源，它用于释放一些内存。建议在对象使用完毕后将其释放。

> 为此，我们将对视频文件剪辑对象使用`close`方法
> 
> **语法:** clip.close()
> 
> **论证:**不需要论证
> 
> **返回:**返回无

下面是实现

```py
# Import everything needed to edit video clips 
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.mp4") 

# getting only first 5 seconds 
clip = clip.subclip(0, 5) 

# showing  clip 
clip.ipython_display(width = 360) 

# releasing the video file clip
clip.close()
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# showing  clip 
clip.ipython_display(width = 360)

# releasing the video file clip
clip.close() 
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```