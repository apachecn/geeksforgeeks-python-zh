# 电影-创建图像序列剪辑

> 原文:[https://www . geesforgeks . org/moviepy-creating-image-sequence-clip/](https://www.geeksforgeeks.org/moviepy-creating-image-sequence-clip/)

在本文中，我们将了解如何在 MoviePy 中创建图像序列剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。图像序列剪辑是通过将图像一个接一个地组合形成一个序列即视频而形成的剪辑。

> 为了做到这一点，我们将使用`ImageSequenceClip`方法
> 
> **语法:**ImageSequenceClip([' image _ file 1 . JPEG '，…]，fps=24)
> 
> **参数:**以图像文件名和 fps 为参数
> 
> **返回:**返回 ImageSequenceClip 对象

下面是实现

```py
# importing editor from movie py
from moviepy.editor import *

# creating a Image sequence clip with fps = 1
clip = ImageSequenceClip(['frame1.png', 'frame2.png', 'frame1.png', 'frame2.png'], fps = 1)

# showing  clip 
clip.ipython_display(width = 360) 
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-466485-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200807000909/140.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200807000909/140.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200807000909/140.mp4)</video>

另一个例子

```py
# importing editor from movie py
from moviepy.editor import *

# creating a Image sequence clip with fps = 3
clip = ImageSequenceClip(['frame1.png', 'frame1.png', 'frame2.png',
                          'frame1.png', 'frame1.png', 'frame2.png',
                          'frame1.png', 'frame1.png', 'frame2.png'], fps = 3)

# showing  clip 
clip.ipython_display(width = 360) 
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-466485-2" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200807000823/234.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200807000823/234.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200807000823/234.mp4)</video>