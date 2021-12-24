# 电影-创建音频剪辑

> 原文:[https://www.geeksforgeeks.org/moviepy-creating-audio-clip/](https://www.geeksforgeeks.org/moviepy-creating-audio-clip/)

在本文中，我们将了解如何在 MoviePy 中创建音频剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。音频剪辑类似于音频文件剪辑，但它是使用 numpy 数组制作的，可以随时编辑和更改。

> 为了做到这一点，我们将使用`AudioClip`方法
> 
> **语法:**音频剪辑(make_frame，持续时间=3)
> 
> **自变量:**以方法和持续时间为自变量
> 
> **返回:**返回音频剪辑对象

下面是实现

```py
# importing editor from movie py
from moviepy.editor import *

# importing numpy
import numpy as np

# method to create a fram
def make_frame(t):
    numpy_array = np.array([1, 2, 4, 1, 3, 4, 5])
    return numpy_array

# creating audio clip
clip = AudioClip(make_frame, duration = 3)

# printing audio clip
print(clip)
```

**输出:**

```py
moviepy.audio.AudioClip.AudioClip object at 0x00000269985E1F88

```

另一个例子

```py
# importing editor from movie py
from moviepy.editor import *

# importing numpy
import numpy as np

# method to create a fram
def make_frame(t):
    numpy_array = np.array([1, 2, 3, 1])*t
    return numpy_array

# creating audio clip
clip = AudioClip(make_frame, duration = 3)

# printing audio clip
print(clip)
```

**输出:**

```py
moviepy.audio.AudioClip.AudioClip object at 0x00000269985E9488

```