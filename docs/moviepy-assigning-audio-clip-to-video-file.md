# 影片–将音频剪辑分配给视频文件

> 原文:[https://www . geesforgeks . org/moviepy-分配-音频-剪辑-视频-文件/](https://www.geeksforgeeks.org/moviepy-assigning-audio-clip-to-video-file/)

在本文中，我们将了解如何在 MoviePy 中将外部音频添加到视频文件剪辑中。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。音频文件格式是用于在计算机系统上存储数字音频数据的文件格式。音频数据的位布局称为音频编码格式，可以解压缩，也可以压缩以减小文件大小，通常使用有损压缩。我们可以借助`AudioFileClip`方法加载音频文件。

> 为此，我们将对视频文件剪辑对象使用`set_audio`属性
> 
> **语法:** clip.set_audio(音频)
> 
> **参数:**它以 AudioFileClip 对象作为参数
> 
> **返回:**返回视频文件剪辑对象

下面是实现

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# loading audio file
audioclip = AudioFileClip("allwell.mp3").subclip(0, 5)

# adding audio to the video clip
videoclip = clip.set_audio(audioclip)

# showing video clip
videoclip.ipython_display()
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

<video class="wp-video-shortcode" id="video-465395-1" width="665" height="374" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200806011225/139.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200806011225/139.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200806011225/139.mp4)</video>

另一个例子

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# loading audio file
audioclip = AudioFileClip("allwell.mp3").subclip(0, 5)

# adding audio to the video clip
videoclip = clip.set_audio(audioclip)

# showing video clip
videoclip.ipython_display()
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

<video class="wp-video-shortcode" id="video-465395-2" width="656" height="404" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200806011204/233.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200806011204/233.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200806011204/233.mp4)</video>