# 电影-创建彩色剪辑

> 原文:[https://www.geeksforgeeks.org/moviepy-creating-color-clip/](https://www.geeksforgeeks.org/moviepy-creating-color-clip/)

在本文中，我们将了解如何在 MoviePy 中创建彩色剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。彩色剪辑基本上是一个剪辑，或者我们可以说是由用户选择颜色的单色图像。

> 为了做到这一点，我们将使用`ColorClip`方法
> 
> **语法:** ColorClip(大小=(460，380)，颜色=[R，G，B])
> 
> **自变量:**它以大小和颜色为自变量
> 
> **返回:**返回颜色剪辑对象

下面是实现

```py
# importing editor from movie py
from moviepy.editor import *

# creating a color clip
# setting it size to be 460 x 380
clip = ColorClip(size =(460, 380), color =[100, 255, 100])

# showing  clip 
clip.ipython_display() 
```

**输出:**
![](img/ff74edafd5c85ffe754669ca6d4e9c47.png)

另一个例子

```py
# importing editor from movie py
from moviepy.editor import *

# creating a color clip
# setting it size to be 200 x 200
clip = ColorClip(size =(200, 200), color =[255, 255, 100])

# showing  clip 
clip.ipython_display() 
```

**输出:**
![](img/a259c07f161b22c7b7cad0577201f4e9.png)