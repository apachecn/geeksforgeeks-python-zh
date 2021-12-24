# 电影合成视频–添加交叉淡入效果

> 原文:[https://www . geesforgeks . org/moviepy-composite-video-add-cross-淡入效果/](https://www.geeksforgeeks.org/moviepy-composite-video-adding-cross-fade-in-effect/)

在本文中，我们将看到如何在 MoviePy 的复合视频文件中添加交叉淡入效果。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。复合的含义是组合不同的元素，复合视频是不同视频剪辑的组合不同于视频文件的堆叠和拼接复合文件易于实现但结构复杂。复合文件将剪辑组合在一起，同时播放，视频播放的位置和时间可以随时设置。“交叉淡入淡出”效果已设置，以便在剪辑更改时发生平滑过渡。交叉淡入是指在电影、广播或电视节目中淡入(声音或图像)，而淡出另一种声音或图像。

> 为此，我们将对视频文件剪辑对象
> **使用交叉渐变方法语法:**剪辑.交叉渐变(n)
> **参数:**它以 float 作为参数
> **返回:**它返回视频文件剪辑对象

下面是实现

## 蟒蛇 3

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 5 seconds
clip1 = clip.subclip(0, 5)

# rotating clip by 180 degree to get the clip3
clip2 = clip1.rotate(180).set_start(4)

# adding cross fade of 2 seconds in the clip2
clip2 = clip2.crossfadein(2.0)

# creating a composite video
final = CompositeVideoClip([clip1, clip2])

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

<video class="wp-video-shortcode" id="video-457865-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722194734/125.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200722194734/125.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722194734/125.mp4)</video>

**另一个例子**

## 蟒蛇 3

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip from it
clip1 = clip.subclip(0, 5)

# mirroring image according to the y axis
clip2 = clip.fx(vfx.mirror_y).set_start(4)

# adding cross fade of 2 seconds in the clip2
clip2 = clip2.crossfadein(2.0)

# creating a composite video
final = CompositeVideoClip([clip1, clip2])

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

<video class="wp-video-shortcode" id="video-457865-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722194646/218.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200722194646/218.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722194646/218.mp4)</video>