# 影片–获取视频文件剪辑的高度

> 原文:[https://www . geesforgeks . org/moviepy-获得视频文件剪辑高度/](https://www.geeksforgeeks.org/moviepy-getting-height-of-video-file-clip/)

在本文中，我们将看到如何在 MoviePy 中获得视频文件的高度。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。高度是视频尺寸的一部分，高度基本上就是视频的长度。

借助下面给出的命令，我们可以加载视频文件剪辑

```
clip = VideoFileClip(file_name)
```

> 为了做到这一点，我们将使用视频文件剪辑对象的`h`属性
> 
> **语法:** clip.h
> 
> **论证:**不需要论证
> 
> **返回:**返回整数

下面是实现

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.webm")

# getting subclip from it
clip1 = clip.subclip(0, 10)

# getting height of the clip
height = clip1.h

# printing value of width
print("Height of clip  : " + str(height))

print("---------------------------------------")

# showing final clip
clip1.ipython_display(width = 480)
```

**输出:**

```
Height of clip  : 480
---------------------------------------
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-457239-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722005741/117.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200722005741/117.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722005741/117.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip from it
clip1 = clip.subclip(0, 7)

# getting height of the clip
height = clip1.h

# printing value of width
print("Height of clip  : " + str(height))

print("---------------------------------------")

# showing final clip
clip1.ipython_display()
```

**输出:**

```
Width of clip  : 404
---------------------------------------
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-457239-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722005847/210.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200722005847/210.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722005847/210.mp4)</video>