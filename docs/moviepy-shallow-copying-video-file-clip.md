# 影片–浅拷贝视频文件剪辑

> 原文:[https://www . geesforgeks . org/moviepy-浅层-复制-视频-文件-剪辑/](https://www.geeksforgeeks.org/moviepy-shallow-copying-video-file-clip/)

在本文中，我们将看到如何在 MoviePy 中浅拷贝视频文件剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。浅拷贝是对象的逐位拷贝。将创建一个新对象，该对象具有原始对象中值的精确副本。如果对象的任何字段是对其他对象的引用，则仅复制引用地址，即仅复制存储器地址。每次剪辑进行输出变换(剪辑、调整大小、剪辑、子剪辑等)时，都会集中使用浅拷贝来生成新剪辑。)

> 为此，我们将对视频文件剪辑对象使用`copy`方法
> 
> **语法:** clip.copy()
> 
> **论证:**不需要论证
> 
> **返回:**返回视频文件剪辑

下面是实现

```
# Import everything needed to edit video clips 
from moviepy.editor import *

# loading video dsa gfg intro video 
clip = VideoFileClip("dsa_geek.mp4") 

# getting only first 5 seconds 
clip = clip.subclip(0, 5) 

# shallow copy the given clip
copied_clip = clip.copy()

# showing  clip 
copied_clip.ipython_display(width = 360) 
```

**输出:**

```
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-475304-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200826001621/1st3.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200826001621/1st3.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200826001621/1st3.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# shallow copy the given clip
copied_clip = clip.copy()

# showing  clip 
copied_clip.ipython_display(width = 360) 
```

**输出:**

```
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-475304-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200826001637/2nd3.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200826001637/2nd3.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200826001637/2nd3.mp4)</video>