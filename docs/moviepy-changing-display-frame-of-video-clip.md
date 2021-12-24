# 电影–更改视频剪辑的显示帧

> 原文:[https://www . geesforgeks . org/moviepy-changing-display-frame-of-video-clip/](https://www.geeksforgeeks.org/moviepy-changing-display-frame-of-video-clip/)

在本文中，我们将了解如何在 MoviePy 中更改视频文件剪辑的显示帧。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。显示帧是单个图像，即视频的单个帧，视频由多个帧组成，我们可以使用 moviepy 更改显示帧。

> 为此，我们将对视频文件剪辑对象
> **使用 fl_image 方法语法:** clip.fl_image(方法)
> **参数:**它以时间方法作为参数
> **返回:**它返回视频文件剪辑对象

下面是实现

## 蟒蛇 3

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# method for inverting image
def invert_image(image):
    return image[:, :, [0, 2, 0]]

# inverting image
final = clip.fl_image(invert_image)

# showing final clip
final.ipython_display()
```

**输出:**

```
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4

```

<video class="wp-video-shortcode" id="video-460222-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200727003836/131.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200727003836/131.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200727003836/131.mp4)</video>

**另一个例子:**

## 蟒蛇 3

```
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting subclip from it
clip = clip.subclip(0, 5)

# method for inverting image
def invert_image(image):
    return image[:, :, [1, 2, 1]]

# inverting image
final = clip.fl_image(invert_image)

# showing final clip
final.ipython_display()
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

<video class="wp-video-shortcode" id="video-460222-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200727003906/224.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200727003906/224.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200727003906/224.mp4)</video>