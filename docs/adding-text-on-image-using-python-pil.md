# 使用 Python 在图像上添加文本–PIL

> 原文:[https://www . geesforgeks . org/add-text-on-image-use-python-pil/](https://www.geeksforgeeks.org/adding-text-on-image-using-python-pil/)

在 Python 中打开一个图像，进行图像编辑，以不同的格式保存该图像一个额外的库称为 **Python 图像库(PIL)** 。使用这个 PIL，我们可以对图像进行许多操作，比如创建新图像、编辑现有图像、旋转图像等。为了添加文本，我们必须遵循给定的方法。

**接近**

*   导入模块
*   打开目标图像
*   使用图像对象添加文本属性
*   显示编辑过图像
*   保存图像

> **语法：** obj.text（ （x，y）， 文本， 来源， 儿子）
> 
> **参数:**
> 
> *   **(x，y):** 这个 X 和 Y 表示在图像上添加文本的开始位置(以像素为单位)/坐标。
> *   **文本:**我们要添加到图像中的文本或消息。
> *   **字体:**具体的你要给文字的字体类型和字号。
> *   **填充:**填充用于给文本赋予字体颜色。

除此之外，我们需要 PIL 的一些模块来执行这项任务。我们需要能够将 2D 图形(形状、文本)添加到图像中的 ImageDraw。此外，我们要求 ImageFont 模块添加自定义字体样式和字体大小。下面给出了向图像添加文本的实现。

**使用的图像:**

![](img/a2bbc5c1038bda03a7d3c6173ba8cb2d.png)

**示例 1:** 给图像添加一个简单的文本。(没有自定义字体样式)

## 蟒蛇 3

```py
# Importing the PIL library
from PIL import Image
from PIL import ImageDraw

# Open an Image
img = Image.open('car.png')

# Call draw Method to add 2D graphics in an image
I1 = ImageDraw.Draw(img)

# Add Text to an image
I1.text((28, 36), "nice Car", fill=(255, 0, 0))

# Display edited image
img.show()

# Save the edited image
img.save("car2.png")
```

**输出:**

![](img/89deda6bab6125234cfbfd05bb213add.png)

在这里，您可以看到我们成功地将文本添加到图像中，但是它并不完全可见，因此我们可以添加字体参数来提供自定义样式。

**示例 2:** 给图像添加一个简单的文本。(使用自定义字体样式)

## 蟒蛇 3

```py
# Importing the PIL library
from PIL import Image
from PIL import ImageDraw
from PIL import ImageFont

# Open an Image
img = Image.open('car.png')

# Call draw Method to add 2D graphics in an image
I1 = ImageDraw.Draw(img)

# Custom font style and font size
myFont = ImageFont.truetype('FreeMono.ttf', 65)

# Add Text to an image
I1.text((10, 10), "Nice Car", font=myFont, fill =(255, 0, 0))

# Display edited image
img.show()

# Save the edited image
img.save("car2.png")
```

**输出:**

![](img/563acaec85f083627f00c650a39cce77.png)