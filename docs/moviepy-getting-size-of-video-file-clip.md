# 影片–获取视频文件剪辑的大小

> 原文:[https://www . geesforgeks . org/moviepy-get-size-of-video-file-clip/](https://www.geeksforgeeks.org/moviepy-getting-size-of-video-file-clip/)

在本文中，我们将了解如何在 MoviePy 中获得视频文件剪辑的大小。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。尺寸基本上是视频的维度，通常视频的维度越高，视频的质量就越高。显示大小不同于视频剪辑的实际大小。

> 为了做到这一点，我们将使用视频文件剪辑对象的`size`属性
> 
> **语法:**剪辑.大小
> 
> **论证:**不需要论证
> 
> **返回:**返回元组

下面是实现

```
# Import everything needed to edit video clips 
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.mp4") 

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# getting clip size
value = clip.size

# printing size
print("Clip Size ", end = " : ")
print(value)

# displaying new clip
clip.ipython_display(width = 420)
```

**输出:**

```
Clip Size  : (854, 480)
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-476070-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200827002306/1st9.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200827002306/1st9.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200827002306/1st9.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# getting clip size
value = clip.size

# printing size
print("Clip Size ", end = " : ")
print(value)

# displaying new clip
clip.ipython_display(width = 420)
```

**输出:**

```
Clip Size  : (656, 404)
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-476070-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200827002455/2nd8.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200827002455/2nd8.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200827002455/2nd8.mp4)</video>