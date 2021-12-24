# 电影-旋转视频文件

> 原文:[https://www.geeksforgeeks.org/moviepy-rotating-video-file/](https://www.geeksforgeeks.org/moviepy-rotating-video-file/)

在本文中，我们将看到如何在 MoviePy 中旋转视频文件剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。旋转是将视频移动或转向其中心点的行为或过程。360 度的旋转将是围绕一个中心点的完整旋转。我们可以以任何角度旋转视频。

> 为此，我们将对视频文件剪辑对象使用`rotate`方法
> 
> **语法:**剪辑.旋转(度)
> 
> **自变量:**以整数为自变量
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

# rotating clip by 45 degree
clip = clip.rotate(45)

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

<video class="wp-video-shortcode" id="video-457229-1" width="665" height="665" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200721203411/download1.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200721203411/download1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200721203411/download1.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip 
clip = clip.subclip(0, 7)

# rotating clip by 180 degree
clip = clip.rotate(180)

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
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-457229-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200721203548/27.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200721203548/27.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200721203548/27.mp4)</video>