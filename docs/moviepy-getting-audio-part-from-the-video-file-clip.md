# 电影-从视频文件剪辑中获取音频部分

> 原文:[https://www . geesforgeks . org/moviepy-从视频文件剪辑中获取音频部分/](https://www.geeksforgeeks.org/moviepy-getting-audio-part-from-the-video-file-clip/)

在本文中，我们将了解如何在 MoviePy 中获取视频文件剪辑的音频部分。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。音频文件格式是用于在计算机系统上存储数字音频数据的文件格式。音频数据的位布局称为音频编码格式，可以解压缩，也可以压缩以减小文件大小，通常使用有损压缩。我们可以借助`AudioFileClip`方法加载音频文件。

> 为此，我们将对视频文件剪辑对象使用`audio`属性
> 
> **语法:**剪辑.音频
> 
> **论证:**不需要论证
> 
> **返回:**返回音频文件剪辑对象

下面是实现

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 3 seconds
clip = clip.subclip(0, 3)

# getting audio from the clip
audioclip = clip.audio

# printing audio clip
print(audioclip)
```

**输出:**

```
moviepy.audio.io.AudioFileClip.AudioFileClip object at 0x0000028BA1F6E488

```

另一个例子

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 3 seconds
clip = clip.subclip(0, 3)

# getting audio from the clip
audioclip = clip.audio

# printing audio clip
print(audioclip)
```

**输出:**

```
None

```