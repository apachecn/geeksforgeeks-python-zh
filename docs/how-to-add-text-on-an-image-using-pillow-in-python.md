# 如何在 Python 中使用枕头在图像上添加文字？

> 原文:[https://www . geesforgeks . org/如何使用 python 中的枕头在图像上添加文本/](https://www.geeksforgeeks.org/how-to-add-text-on-an-image-using-pillow-in-python/)

**先决条件:**T2】PIL

在本文中，我们将看到如何使用 Python 中的枕头库在图像上添加文本。Python 图像库(PIL)是 Python 语言事实上的图像处理包。它集成了轻量级图像处理工具，有助于编辑、创建和保存图像。枕头支持多种图像文件格式，包括 BMP、PNG、JPEG 和 TIFF。

### **使用的方法**

**语法:**

```
ImageDraw.Draw.text((x, y),"Text",(r,g,b))
```

### 方法

*   导入模块
*   导入图像
*   添加文本
*   保存图像

**使用中的图像:**

![](img/2dfcae72432a037761de0862c3a93d24.png)

**例 1:**

## 蟒蛇 3

```
from PIL import Image
from PIL import ImageFont
from PIL import ImageDraw

# importing the image
img = Image.open("gfg.png")
draw = ImageDraw.Draw(img)

# specifying coordinates and colour of text
draw.text((50, 90), "Sample Text", (255, 255, 255))

# saving the image
img.save('sample.jpg')
```

**输出:**

![](img/5a3c39cfef6a43fff46e68a352425ac2.png)

**示例 2:** 以特定字体书写文本

要以特定字体书写文本，我们需要下载所需字体的字体文件。在下面给出的例子中，我们已经使用了漫画无，它可以从:[https://www.wfonts.com/font/comic-sans-ms](https://www.wfonts.com/font/comic-sans-ms)下载

## 蟒蛇 3

```
from PIL import Image
from PIL import ImageFont
from PIL import ImageDraw

# importing the image
img = Image.open("gfg.png")
draw = ImageDraw.Draw(img)

# loading the font and providing the size
font = ImageFont.truetype("ComicSansMS3.ttf", 30)

# specifying coordinates and colour of text
draw.text((50, 90), "Hello World!", (255, 255, 255), font=font)

# saving the image
img.save('sample.jpg')
```

**输出:**

![](img/17c1b47a9bcbc52280dc8f7e7b54d2ff.png)