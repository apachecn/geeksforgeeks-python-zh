# 电影-将视频文件保存为 GIF

> 原文:[https://www . geesforgeks . org/moviepy-saving-video-file-as-gif/](https://www.geeksforgeeks.org/moviepy-saving-video-file-as-gif/)

在本文中，我们将了解如何在 MoviePy 中将视频文件剪辑保存为 GIF。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。图形交换格式是一种位图图像格式，由在线服务提供商 CompuServe 的一个团队开发。

> 为此，我们将对视频文件剪辑对象使用`write_gif`方法
> 
> **语法:** clip.write_gif(名称)
> 
> **参数:**以字符串即文件名为参数
> 
> **返回:**返回无

下面是实现

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 3 seconds
clip = clip.subclip(0, 3)

# saving video clip as gif
clip.write_gif("gfg_gif.gif")

# loading  gif
gif = VideoFileClip("gfg_gif.gif")

# showing gif
gif.ipython_display()
```

**输出:**

```
MoviePy - Building file gfg_gif.gif with imageio.

Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-465391-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200805224021/137.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200805224021/137.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200805224021/137.mp4)</video>

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 3 seconds
clip = clip.subclip(0, 3)

# saving video clip as gif
clip.write_gif("intro_gif.gif")

# loading  gif
gif = VideoFileClip("intro_gif.gif")

# showing gif
gif.ipython_display()
```

**输出:**

```
MoviePy - Building file intro_gif.gif with imageio.

Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-465391-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200805223958/231.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200805223958/231.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200805223958/231.mp4)</video>