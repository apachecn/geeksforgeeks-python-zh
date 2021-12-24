# pgmagick–在图像中添加文本

> 原文:[https://www.geeksforgeeks.org/pgmagick-add-text-in-images/](https://www.geeksforgeeks.org/pgmagick-add-text-in-images/)

在本文中，我们将看到如何使用 Python 中的 pgmagick 库向图像添加文本。我们可以通过使用`annotate()`功能来做到这一点。有时，我们需要向图像添加文本，例如图像的版权或与图像相关的组织名称。

在本文中，我们将创建一个带有绿色背景文本“GeeksforGeeks”的图像，并在其上操作文本。

```
# importing library
from pgmagick.api import Image

# using image function
img = Image((300, 300), 'green')
img.annotate('GeeksforGeeks')
img.write('GeeksforGeeks.jpg')
```

**输出:**
![](img/b13658110af6a657aac42a04af396ac4.png)

现在，我们将文本旋转到 45 度。

```
# importing library
from pgmagick.api import Image

img = Image((300, 300), 'green')

# annotate function 
img.annotate('GeeksforGeeks', angle = 45)
img.write('geeksforgeeks.png')
```

![](img/f431cf4a6ca9a96460b57c79fd5973d9.png)

现在我们将改变字体以及文本的大小。

```
# importing library
from pgmagick.api import Image

img = Image((300, 200), 'green')
img.font("/usr/share/fonts/truetype/ttf-japanese-gothic.ttf")
img.font_pointsize(26)

# annotate function 
img.annotate('GeeksforGeeks')
img.write('GeeksforGeeks.png')
```

**输出:**
![](img/9242d501fd1d6633292a201332ef3c82.png)