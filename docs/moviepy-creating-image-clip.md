# 电影-创建图像剪辑

> 原文:[https://www.geeksforgeeks.org/moviepy-creating-image-clip/](https://www.geeksforgeeks.org/moviepy-creating-image-clip/)

在本文中，我们将看到如何在 MoviePy 中创建文本剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。图像剪辑基本上是一个剪辑，或者我们可以说是由用户加载的单个图像。

> 为了做到这一点，我们将使用`ImageClip`方法
> 
> **语法:** ImageClip(名称)
> 
> **参数:**以文件名即字符串为参数
> 
> **返回:**返回 ImageClip 对象

下面是实现

```
# importing editor from movie py
from moviepy.editor import *

# file name
name = "frame1.png"

# creating a image clip
clip = ImageClip(name)

# showing  clip 
clip.ipython_display() 
```

**输出:**
![](img/a969bb0c51f99a0455773fb524ea697d.png)

另一个例子

```
# importing editor from movie py
from moviepy.editor import *

# file name
name = "frame2.png"

# creating a image clip
clip = ImageClip(name)

# showing  clip 
clip.ipython_display() 
```

**输出:**
![](img/cc90bfcf4193906c6881f3e85c586130.png)