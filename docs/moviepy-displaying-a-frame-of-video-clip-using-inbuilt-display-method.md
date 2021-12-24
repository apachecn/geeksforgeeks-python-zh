# 电影-使用内置显示方法显示一帧视频剪辑

> 原文:[https://www . geesforgeks . org/moviepy-显示一帧视频剪辑-使用内置显示方法/](https://www.geeksforgeeks.org/moviepy-displaying-a-frame-of-video-clip-using-inbuilt-display-method/)

在本文中，我们将了解如何使用内置显示方法在 MoviePy 中显示给定时间的单帧视频文件剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。借助`save_frame`方法，我们可以随时存储特定的帧，借助`show`方法可以显示。Show 方法使用 PyGame 窗口，因为内置的显示方法不需要任何窗口。

> 为此，我们将对视频文件剪辑对象使用`clip.ipython_display`方法
> 
> **语法:**clip . clip . ipython _ display(t = 2)
> 
> **论证:**需要时间作为论证
> 
> **返回:**返回无

下面是实现

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# displaying a frame
clip.ipython_display(t = 2)
```

**输出:**
![](img/f678e7971b11f937877315be0295ea7c.png)

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# displaying a frame
clip.ipython_display(t = 2)
```

**输出:**

![](img/8866ecccf4a9f66311f0bf8abcb98c8a.png)