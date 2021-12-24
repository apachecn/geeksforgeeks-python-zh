# 电影-连接多个视频文件

> 原文:[https://www . geesforgeks . org/moviepy-串联-多个-视频-文件/](https://www.geeksforgeeks.org/moviepy-concatenating-multiple-video-files/)

在本文中，我们将看到如何在 MoviePy 中连接多个视频文件剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。在形式语言理论和计算机编程中，字符串串联是将字符串首尾相连的操作。例如，“雪”和“球”的连接是“雪球”，类似地，连接多个视频剪辑意味着它们将被一个接一个地播放，并充当单个视频文件。
**注意:**剪辑不需要大小相同。如果它们的大小不同，它们都将出现在一个足够大的剪辑中心，以容纳其中最大的一个。

> 为了做到这一点，我们将使用 concatenate_videoclips 方法
> **语法:**concatenate _ video clips(clips)
> **参数:**它以视频文件剪辑列表作为参数
> **返回:**它返回 VideoFileClip 对象

下面是实现

## 蟒蛇 3

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting subclip as video is large
clip1 = clip.subclip(0, 5)

# getting subclip as video is large
clip2 = clip.subclip(60, 65)

# concatenating both the clips
final = concatenate_videoclips([clip1, clip2])
#writing the video into a file / saving the combined video
final.write_videofile("merged.webm")

# showing final clip
final.ipython_display(width = 480)
```

**输出:**

```
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-457231-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722000804/114.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200722000804/114.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722000804/114.mp4)</video>

**另一个例子:**

## 蟒蛇 3

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting subclip as video is large
clip1 = clip.subclip(0, 5)

# loading video gfg
clipx = VideoFileClip("geeks.mp4")

# getting subclip
clip2 = clipx.subclip(0, 5)

# clip list
clips = [clip1, clip2]

# concatenating both the clips
final = concatenate_videoclips(clips)

# showing final clip
final.ipython_display(width = 480)
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

<video class="wp-video-shortcode" id="video-457231-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722001141/download-1.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200722001141/download-1.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722001141/download-1.mp4)</video>