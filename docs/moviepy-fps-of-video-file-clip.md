# 影片–视频文件剪辑的 FPS

> 原文:[https://www . geesforgeks . org/moviepy-fps-of-video-file-clip/](https://www.geeksforgeeks.org/moviepy-fps-of-video-file-clip/)

在本文中，我们将了解如何在 MoviePy 中获得视频文件的每秒帧数(帧率)。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。帧率是那些图像显示的速度，或者你“翻看”这本书的速度，通常用“每秒帧数”或 FPS 来表示。每幅图像代表一帧，因此如果一个视频以 24fps 的速度被捕获和回放，这意味着视频的每一秒钟显示 24 幅不同的静止图像。

借助下面给出的命令，我们可以加载视频文件剪辑

```py
clip = VideoFileClip(file_name)
```

> 为了做到这一点，我们将使用视频文件剪辑对象的`fps`属性
> 
> **语法:** clip.fps
> 
> **论证:**不需要论证
> 
> **返回:**返回浮动

下面是实现

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.webm").subclip(0, 10)

# getting frame rate of the clip
rate = clip.fps

# printing the fps
print("FPS : " + str(rate))

print("---------------------------------------")

# showing final clip
clip.ipython_display()
```

**输出:**

```py
FPS : 29.97002997002997
---------------------------------------
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-457243-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722013754/119.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200722013754/119.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722013754/119.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip from it
clip1 = clip.subclip(0, 7)

# getting frame rate of the clip
rate = clip1.fps

# printing the fps
print("FPS : " + str(rate))

print("---------------------------------------")

# showing final clip
clip1.ipython_display()
```

**输出:**

```py
FPS : 60.0
---------------------------------------
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-457243-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722013838/212.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200722013838/212.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722013838/212.mp4)</video>