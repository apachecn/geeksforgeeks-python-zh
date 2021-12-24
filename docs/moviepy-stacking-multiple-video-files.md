# 影片–堆叠多个视频文件

> 原文:[https://www . geesforgeks . org/moviepy-stacking-multi-video-file/](https://www.geeksforgeeks.org/moviepy-stacking-multiple-video-files/)

在本文中，我们将看到如何在 MoviePy 中堆叠多个视频文件剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。不像在堆叠中连接多个视频剪辑，所有视频文件像拼贴画中的图像一样同时播放。
**注意:**剪辑不需要大小相同。如果它们的大小不同，它们都将出现在一个足够大的剪辑中心，以容纳其中最大的一个

> 为此，我们将使用 clips_array 方法
> **语法:** clips_array(clips)
> **参数:**它以视频文件剪辑列表作为参数
> **返回:**它返回 VideoFileClip 对象

下面是实现

## 蟒蛇 3

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video and getting only first 5 seconds
clip1 = VideoFileClip("dsa_geek.webm").subclip(0, 5)

# rotating clip1 by 90 degree to get the clip2
clip2 = clip1.rotate(90)

# rotating clip1 by 180 degree to get the clip3
clip3 = clip1.rotate(180)

# rotating clip1 by 270 degree to get the clip4
clip4 = clip1.rotate(270)

# list of clips
clips = [[clip1, clip2],
        [clip3, clip4]]

# stacking clips
final = clips_array(clips)

# showing final clip
final.ipython_display(width = 480)
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-457233-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722002821/115.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200722002821/115.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722002821/115.mp4)</video>

另一个例子

## 蟒蛇 3

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
# getting subclip as video is large
# adding margin to the video
clip1 = VideoFileClip("geeks.mp4").subclip(0, 5).margin(10)

# getting clip2 by mirroring over x axis
clip2 = clip1.fx(vfx.mirror_x)

# getting clip3 by mirroring over y axis
clip3 = clip1.fx(vfx.mirror_y)

# getting clip 4 by resising the clip
clip4 = clip1.resize(0.60)

# clips list
clips = [[clip1, clip2],
        [clip3, clip4]]

# stacking clips
final = clips_array(clips)

# showing final clip
final.ipython_display(width = 480)
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

<video class="wp-video-shortcode" id="video-457233-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200722003028/28.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200722003028/28.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200722003028/28.mp4)</video>