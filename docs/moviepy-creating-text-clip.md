# 电影-创建文本剪辑

> 原文:[https://www.geeksforgeeks.org/moviepy-creating-text-clip/](https://www.geeksforgeeks.org/moviepy-creating-text-clip/)

在本文中，我们将看到如何在 MoviePy 中创建文本剪辑。MoviePy 是一个用于视频编辑的 Python 模块，可用于视频和 GIF 的基本操作。视频是由帧组成的，帧的组合创建了一个视频，每一帧都是一个独立的图像。文本剪辑基本上是一个剪辑，这里我们可以说它是包含文本的图像。

> 为了做到这一点，我们将使用`TextClip`方法
> 
> **语法:**文字片段(文字)
> 
> **参数:**以字符串为必要参数，颜色大小等造型效果为可选参数
> 
> **返回:**返回文本剪辑对象

下面是实现

```
# importing editor from movie py
from moviepy.editor import *

# text
text = "GeeksforGeeks"

# creating a text clip
# having font arial-bold
# with font size = 70
# and color = green
clip = TextClip(text, font ="Arial-Bold", fontsize = 70, color ="green")

# showing  clip 
clip.ipython_display() 
```

**输出:**
![](img/0bac26cf24ad2d7031ed152f56416db0.png)

另一个例子

```
# importing editor from movie py
from moviepy.editor import *

# text
text = "Hello"

# creating a text clip
# having font arial-bold
# with font size = 50
# and color = black
clip = TextClip(text, font ="Arial-Bold", fontsize = 50, color ="black")

# showing  clip 
clip.ipython_display() 
```

**输出:**
![](img/967a7bbe03db42c188760d27cdde917c.png)