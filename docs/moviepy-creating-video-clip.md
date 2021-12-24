# 电影-创建视频剪辑

> 原文:[https://www.geeksforgeeks.org/moviepy-creating-video-clip/](https://www.geeksforgeeks.org/moviepy-creating-video-clip/)

在本文中，我们将了解如何在 MoviePy 中创建视频剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。视频剪辑是 MoviePy 中所有其他视频剪辑的基类。如果你只想编辑视频文件，我们永远都不需要。当我们想要从另一个库生成的帧制作动画时，这个类是实用的。我们只需要定义一个函数 make_frame(t)，它返回一个 HxWx3 numpy 数组(由 8 位整数组成)，表示时间 t 的帧。

> 为此，我们将使用视频剪辑方法
> **语法:**视频剪辑(make_frame，duration)
> **参数:**它以方法和持续时间作为参数
> **返回:**它返回视频剪辑对象

下面是实现

## 蟒蛇 3

```py
# importing matplotlib and numpy
import matplotlib.pyplot as plt
import numpy as np

# importing movie py libraries
from moviepy.editor import VideoClip
from moviepy.video.io.bindings import mplfig_to_npimage

# numpy array
x = np.linspace(-2, 2, 200)

# matplot subplot
fig, ax = plt.subplots()
duration = 2

# method to get frames
def make_frame(t):

    # clear
    ax.clear()

    # plotting line
    ax.plot(x, np.sin(x + 2 * np.pi / duration * t), lw = 3)
    ax.set_ylim(-1.5, 2.5)

    # returning numpy image
    return mplfig_to_npimage(fig)

# creating Video Clip
clip = VideoClip(make_frame, duration = 3)

# displaying clip
clip .ipython_display(fps = 20, loop = True, autoplay = True)
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-466495-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200807012826/141.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20200807012826/141.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200807012826/141.mp4)</video>

另一个例子

## 蟒蛇 3

```py
# importing matplotlib and numpy
import matplotlib.pyplot as plt
import numpy as np

# importing movie py libraries
from moviepy.editor import VideoClip
from moviepy.video.io.bindings import mplfig_to_npimage

# numpy array
x = np.linspace(-4, 4, 100)

# matplot subplot
fig, ax = plt.subplots()

duration = 2

# method to get frames
def make_frame(t):

    # clear
    ax.clear()

    # plotting line
    ax.plot(x, np.cos(x + 4 * np.pi / duration * t), lw = 3)
    ax.set_ylim(-1.5, 2.5)

    # returning mumpy image
    return mplfig_to_npimage(fig)

# creating Video Clip
clip = VideoClip(make_frame, duration = 3)

# displaying clip
clip .ipython_display(fps = 20, loop = True, autoplay = True)
```

**输出:**

```py
Moviepy - Building video __temp__.mp4.
Moviepy - Writing video __temp__.mp4

Moviepy - Done !
Moviepy - video ready __temp__.mp4
```

<video class="wp-video-shortcode" id="video-466495-2" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20200807012748/235.mp4?_=2">[https://media.geeksforgeeks.org/wp-content/uploads/20200807012748/235.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20200807012748/235.mp4)</video>