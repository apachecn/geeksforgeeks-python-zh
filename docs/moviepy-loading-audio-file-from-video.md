# 电影-从视频加载音频文件

> 原文:[https://www . geesforgeks . org/moviepy-loading-audio-file-from-video/](https://www.geeksforgeeks.org/moviepy-loading-audio-file-from-video/)

在本文中，我们将看到如何在 MoviePy 中从视频文件剪辑加载音频文件。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。音频文件格式是用于在计算机系统上存储数字音频数据的文件格式。音频数据的位布局称为音频编码格式，可以解压缩，也可以压缩以减小文件大小，通常使用有损压缩。

> 为了做到这一点，我们将使用`AudioFileClip`方法
> 
> **语法:**音频文件剪辑(“some_video.avi”)
> 
> **参数:**以视频文件名为参数
> 
> **返回:**返回音频文件剪辑对象

下面是实现

```py
# importing editor from movie py
from moviepy.editor import *

# loading audio file from the video
audioclip = AudioFileClip("geeks.mp4")

# printibg audio clip
print(audioclip)
```

**输出:**

```py
moviepy.audio.io.AudioFileClip.AudioFileClip object at 0x0000028BA2050F08

```

另一个例子

```py
# importing editor from movie py
from moviepy.editor import *

# loading audio file
audioclip = AudioFileClip("dsa_geek.mp4")

# printibg audio clip
print(audioclip)
```

**输出:**

```py
moviepy.audio.io.AudioFileClip.AudioFileClip object at 0x0000028BA203B1C8

```