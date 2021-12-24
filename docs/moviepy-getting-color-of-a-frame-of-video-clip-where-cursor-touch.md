# 运动-获取光标触摸的视频剪辑帧的颜色

> 原文:[https://www . geesforgeks . org/moviepy-获取视频剪辑的帧颜色-光标触摸的位置/](https://www.geeksforgeeks.org/moviepy-getting-color-of-a-frame-of-video-clip-where-cursor-touch/)

在本文中，我们将看到如何在 MoviePy 中的视频文件剪辑的给定时间获得单帧的颜色。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。借助带有 VideoFileClip 对象的 save_frame 方法，我们可以随时存储特定的帧。通过打开交互，我们可以得到光标点击的位置和颜色。

clip.show 方法允许预览一个剪辑的一个帧，而不必将其写入文件:以下几行在 PyGame 窗口中显示该帧

> 为此，我们将对 VideoFileClip 对象
> **使用 show 方法语法:** clip.show(t，interactive = True)
> **参数:**需要时间，迭代= True 作为参数
> **返回:**返回 None

下面是实现

## 蟒蛇 3

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video dsa gfg intro video
clip = VideoFileClip("dsa_geek.webm")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# showing frame at 2 second
clip.show(2, interactive = True)
```

**输出:**

```py
position, color :  (262, 174), [246 135 102]
position, color :  (566, 131), [251 255 255]
position, color :  (227, 269), [38 38 38]
position, color :  (419, 319), [255 255 255] 
```

<video class="wp-video-shortcode" id="video-462406-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200730184659/MoviePy-2020-07-30-18-46-11.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200730184659/MoviePy-2020-07-30-18-46-11.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200730184659/MoviePy-2020-07-30-18-46-11.mp4)</video>

**另一个例子**

## 蟒蛇 3

```py
# Import everything needed to edit video clips
from moviepy.editor import *

# loading video gfg
clip = VideoFileClip("geeks.mp4")

# getting only first 5 seconds
clip = clip.subclip(0, 5)

# showing frame at 3 second
clip.show(3, interactive = True)
```

**输出:**

```py
position, color :  (248, 305), [239 239 239]
position, color :  (136, 93), [239 239 239]
position, color :  (229, 181), [ 17 147   6]
position, color :  (122, 83), [239 239 239]
position, color :  (358, 125), [239 239 239]
```

<video class="wp-video-shortcode" id="video-462406-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200730184912/MoviePy-2020-07-30-18-48-46.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200730184912/MoviePy-2020-07-30-18-48-46.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200730184912/MoviePy-2020-07-30-18-48-46.mp4)</video>