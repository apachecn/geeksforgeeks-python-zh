# 移动–设置剪辑的 FPS

> 原文:[https://www . geesforgeks . org/moviepy-setting-fps-of-the-clip/](https://www.geeksforgeeks.org/moviepy-setting-fps-of-the-clip/)

在本文中，我们将看到如何在 MoviePy 中设置视频文件剪辑的 fps。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。帧速率是连续图像(称为帧)出现在显示器上的频率。该术语同样适用于电影和摄像机、计算机图形和动作捕捉系统。帧率也可以称为帧频，用赫兹表示。

> 为此，我们将对视频文件剪辑对象使用`set_fps`方法
> 
> **语法:** clip.set_fps(n)
> 
> **自变量:**取整数值作为自变量
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

# new clip with new fps
new_clip = clip.set_fps(5)

# displaying new clip
new_clip.ipython_display(width = 360)
```

**输出:**

```
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-475317-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200826030526/1st8.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200826030526/1st8.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200826030526/1st8.mp4)</video>
Another example

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# new clip with new fps
new_clip = clip.set_fps(100)

# displaying new clip
new_clip.ipython_display(width = 360)
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

<video class="wp-video-shortcode" id="video-475317-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200826030612/2nd7.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200826030612/2nd7.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200826030612/2nd7.mp4)</video>