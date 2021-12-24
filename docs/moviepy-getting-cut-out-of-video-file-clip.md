# 影片–从视频文件剪辑中剪切出来

> 原文:[https://www . geesforgeks . org/moviepy-get-cut-out-of-video-file-clip/](https://www.geeksforgeeks.org/moviepy-getting-cut-out-of-video-file-clip/)

在本文中，我们将看到如何在 MoviePy 中获得视频文件剪辑的剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。剪切视频是经过修剪的视频，或者我们可以说它是从原始视频中剪切下来的几秒钟，它被用来跳过视频的某个部分。剪切是指从原始视频中获得视频，并在视频之间跳过一段时间。

> 为此，我们将对视频文件剪辑对象使用`cutout`方法
> 
> **语法:**剪辑.剪切(ts，te)
> 
> **自变量:**取两个整数作为自变量(开始和结束时间跳过)
> 
> **返回:**返回视频文件剪辑

下面是实现

```
# Import everything needed to edit video clips 
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.mp4") 

# getting only first 5 seconds 
clip = clip.subclip(0, 15) 

# cutting out some part from the clip
clip = clip.cutout(3, 10)

# showing  clip 
clip.ipython_display(width = 360) 
```

**输出:**

```
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-475307-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200826004714/1st4.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200826004714/1st4.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200826004714/1st4.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# getting only first 5 seconds 
clip = clip.subclip(0, 10) 

# cutting out some part from the clip
clip = clip.cutout(3, 7)

# showing  clip 
clip.ipython_display(width = 360) 
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

<video class="wp-video-shortcode" id="video-475307-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200826004732/2nd4.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200826004732/2nd4.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200826004732/2nd4.mp4)</video>