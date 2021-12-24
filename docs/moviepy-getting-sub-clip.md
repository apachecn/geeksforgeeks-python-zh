# 电影-获取子剪辑

> 原文:[https://www.geeksforgeeks.org/moviepy-getting-sub-clip/](https://www.geeksforgeeks.org/moviepy-getting-sub-clip/)

在本文中，我们将了解如何在 MoviePy 中显示视频文件剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。子片段是您想要在项目中单独编辑和管理的主(源)片段的一部分。您可以使用子片段来组织长媒体文件。您可以像处理主片段一样，在时间线面板中处理子片段。修剪和编辑子片段受其起点和终点的约束。剪辑有助于克服一次显示大视频时出现的内存错误。

> 为此，我们将对视频文件剪辑对象使用`subclip`方法
> 
> **语法:** clip.subclip(i，j)
> 
> **参数:**取两个整数参数，以秒为单位为起始值和结束值
> 
> **返回:**返回视频文件剪辑对象

下面是实现

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting subclip as video is large
clip = clip.subclip(55, 65)

# showing clip
clip.ipython_display(width = 480)
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-456656-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200721162534/112.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200721162534/112.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200721162534/112.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip 
clip = clip.subclip(0, 7)

# showing clip
clip.ipython_display()
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp
```

<video class="wp-video-shortcode" id="video-456656-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200721162634/25.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200721162634/25.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200721162634/25.mp4)</video>