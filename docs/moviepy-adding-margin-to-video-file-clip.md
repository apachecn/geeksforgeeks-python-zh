# 影片–为视频文件剪辑添加边距

> 原文:[https://www . geesforgeks . org/moviepy-视频文件添加边距-剪辑/](https://www.geeksforgeeks.org/moviepy-adding-margin-to-video-file-clip/)

在本文中，我们将了解如何在 MoviePy 中为视频文件剪辑添加边距。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。在版式设计中，边距是页面主要内容和页面边缘之间的区域。边距有助于定义文本行的开始和结束位置。当页面对齐时，文本会展开，与左右边距齐平，同样，视频文件剪辑的边距会在视频和主帧之间增加额外的空间。

> 为此，我们将对视频文件剪辑对象使用`margin`方法
> 
> **语法:** clip.margin(n)
> 
> **自变量:**以整数为自变量
> 
> **返回:**返回视频文件剪辑对象

下面是实现

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.webm")

# getting subclip from the original video
clip = clip.subclip(0, 10)

# adding margin to the video
clip = clip.margin(40)

# showing final clip
clip.ipython_display()
```

**输出:**

```
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-457221-1" width="665" height="399" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722093649/120.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200722093649/120.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722093649/120.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip from it
clip1 = clip.subclip(0, 7)

# adding margin to the clip
clip1 = clip1.margin(20)

# showing final clip
clip1.ipython_display()
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

<video class="wp-video-shortcode" id="video-457221-2" width="665" height="424" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722093629/213.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200722093629/213.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722093629/213.mp4)</video>