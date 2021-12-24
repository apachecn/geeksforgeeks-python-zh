# 影片–视频文件剪辑的迭代帧

> 原文:[https://www . geesforgeks . org/moviepy-iterating-frames-of-video-file-clip/](https://www.geeksforgeeks.org/moviepy-iterating-frames-of-video-file-clip/)

在本文中，我们将看到如何在 MoviePy 中迭代视频文件剪辑的帧。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。一个视频基本上是每次有一个特定的帧的许多帧的组合，为了在给定的时间获得帧，我们使用 get_frame 方法。迭代帧意味着遍历帧，帧以 numpy ndarray 的形式表示。

> 为此，我们将使用 iter_frames 方法和 VideoFileClip 对象
> **语法:** clip.iter_frames()
> **参数:**它不需要参数
> **返回:**它返回 Clip.iter_frames

下面是实现

## 蟒蛇 3

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# iterating frames
frames = clip.iter_frames()

# counter to count the frames
counter = 0

# using loop to transverse the frames
for value in frames:

    # incrementing the counter
    counter += 1

# printing the value of the counter
print("Counter Value ", end = " : ")
print(counter)

# showing  clip
clip.ipython_display(width = 360)
```

**输出:**

```py
Counter Value  : 150
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-475311-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200825235530/1st2.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200825235530/1st2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200825235530/1st2.mp4)</video>

另一个例子

## 蟒蛇 3

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# iterating frames
frames = clip.iter_frames()

# counter to count the frames
counter = 0

# using loop to transverse the frames
for value in frames:

    # incrementing the counter
    counter += 1

# printing the value of the counter
print("Counter Value ", end = " : ")
print(counter)

# showing  clip
clip.ipython_display(width = 360)
```

**输出:**

```py
Counter Value  : 300
Moviepy - Building video __temp__.mp4.
MoviePy - Writing audio in __temp__TEMP_MPY_wvf_snd.mp3

MoviePy - Done.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-475311-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200825235546/2nd2.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200825235546/2nd2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200825235546/2nd2.mp4)</video>