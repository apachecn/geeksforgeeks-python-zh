# 电影-调整视频文件大小

> 原文:[https://www.geeksforgeeks.org/moviepy-resizing-video-file/](https://www.geeksforgeeks.org/moviepy-resizing-video-file/)

在本文中，我们将看到如何在 MoviePy 中调整视频文件剪辑的大小。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。调整视频文件大小意味着。当您将 vdideo 的帧从一个像素网格调整到另一个像素网格时，会发生图像/帧插值。当我们需要增加或减少像素总数时，调整视频大小是必要的，而当您校正镜头失真或旋转视频时，可能会发生重新映射。

> 为此，我们将对视频文件剪辑对象使用`resize`方法
> 
> **语法:** clip.resize(n)
> 
> **参数:**取浮点值，即乘数
> 
> **返回:**返回视频文件剪辑对象

下面是实现

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video and getting only first 5 seconds
clip1 = VideoFileClip("dsa_geek.webm").subclip(0, 5)

# getting width and height of clip 1
w1 = clip1.w
h1 = clip1.h

print("Width x Height of clip 1 : ", end = " ")
print(str(w1) + " x ", str(h1))

print("---------------------------------------")

# resizing video downsize 50 % clip2 = clip1.resize(0.5)

# getting width and height of clip 1
w2 = clip2.w
h2 = clip2.h

print("Width x Height of clip 2 : ", end = " ")
print(str(w2) + " x ", str(h2))

print("---------------------------------------")

# showing final clip
clip2.ipython_display(width = 480)
```

**输出:**

```
Width x Height of clip 1 :  854 x  480
---------------------------------------
Width x Height of clip 2 :  427 x  240
---------------------------------------
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-457235-1" width="427" height="240" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722004427/116.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200722004427/116.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722004427/116.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip
clip1 = clip.subclip(0, 7)

# getting width and height of clip 1
w1 = clip1.w
h1 = clip1.h

print("Width x Height of clip 1 : ", end = " ")
print(str(w1) + " x ", str(h1))

print("---------------------------------------")

# resizing video downsize 50 % clip2 = clip1.resize(0.5)

# getting width and height of clip 1
w2 = clip2.w
h2 = clip2.h

print("Width x Height of clip 2 : ", end = " ")
print(str(w2) + " x ", str(h2))

print("---------------------------------------")

# showing final clip
clip2.ipython_display()
```

**输出:**

```
Width x Height of clip 1 :  656 x  404
---------------------------------------
Width x Height of clip 2 :  328 x  202
---------------------------------------
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-457235-2" width="328" height="202" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722004527/29.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200722004527/29.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722004527/29.mp4)</video>