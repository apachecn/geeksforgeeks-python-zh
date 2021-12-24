# 用 Python 创建 PDF 文档

> 原文:[https://www . geesforgeks . org/creating-pdf-documents-with-python/](https://www.geeksforgeeks.org/creating-pdf-documents-with-python/)

在本文中，我们将学习如何用 Python 创建 pdf。一个非常著名的名为 pypdf2 的模块用于修改和读取现有的 pdf，但它的主要缺点是不能创建新的 pdf 文件。因此，今天我们希望了解另一个名为 reportlab 的 python 模块，它可以帮助我们创建新的 pdf 文件，并在上面编辑我们内心的内容。

**所需模块:**

**Reportlab:** 本模块用于处理 PDF 文件。

```
pip install reportlab
```

**分步方法:**

**第一步:**

我们从导入模块和类开始。Canvas 用于在 pdf 上绘制东西，ttfonts 和 pdfmetrics 将帮助我们在 pdf 中使用自定义的 TTF 字体，而 colors 将帮助我们轻松挑选颜色，而无需记住它们的十六进制值。

## 蟒蛇 3

```
# importing modules
from reportlab.pdfgen import canvas
from reportlab.pdfbase.ttfonts import TTFont
from reportlab.pdfbase import pdfmetrics
from reportlab.lib import colors
```

**第二步:**

接下来，我们将文档中所有需要编写和绘制的内容初始化为特定的变量，以便在需要时调用它们。

## 蟒蛇 3

```
# initializing variables with values
fileName = 'sample.pdf'
documentTitle = 'sample'
title = 'Technology'
subTitle = 'The largest thing now!!'
textLines = [
    'Technology makes us aware of',
    'the world around us.',
]
image = 'image.jpg'
```

**第三步:**

接下来，我们用 pdf 的名称初始化一个画布对象，并将标题设置为 documentTitle。

## 蟒蛇 3

```
# creating a pdf object
pdf = canvas.Canvas(fileName)

# setting the title of the document
pdf.setTitle(documentTitle)
```

**第四步:**

接下来，我们使用 pdfmetrics 和 TTFont 将外部字体注册到 reportlab 字体中，并为其分配一个名称。接下来，我们设置新字体的大小。然后，我们使用 drawCentredString 函数在 pdf 上绘制字符串，该函数将 x 和 y 值作为要写入的文本的中心，并相应地调整文本的左、右、上和下。注意，我们需要 TTF 文件出现在文件夹中来执行命令。

## 蟒蛇 3

```
# registering a external font in python
pdfmetrics.registerFont(
    TTFont('abc', 'SakBunderan.ttf')
)

# creating the title by setting it's font
# and putting it on the canvas
pdf.setFont('abc', 36)
pdf.drawCentredString(300, 770, title)
```

**第五步:**

接下来对于字幕，我们做同样的事情，除了这次字幕的颜色是蓝色，这次我们使用的是 reportlab 自带的标准字体。

## 蟒蛇 3

```
# creating the subtitle by setting it's font,
# colour and putting it on the canvas
pdf.setFillColorRGB(0, 0, 255)
pdf.setFont("Courier-Bold", 24)
pdf.drawCentredString(290, 720, subTitle)
```

**第六步:**

接下来，我们画一条线，然后在列表中输入前面定义的几行文本。第一行定义了文本的起始 x 和 y 位置。接下来的两行设置文本的字体、字号和字体颜色。接下来的两行遍历列表中的每个元素，并将其作为一行添加到文本中。最后一行将文本绘制到屏幕上。

## 蟒蛇 3

```
# drawing a line
pdf.line(30, 710, 550, 710)

# creating a multiline text using
# textline and for loop
text = pdf.beginText(40, 680)
text.setFont("Courier", 18)
text.setFillColor(colors.red)

for line in textLines:
    text.textLine(line)

pdf.drawText(text)
```

**第七步:**

最后，我们使用 drawInlineImage 函数在 pdf 上绘制一张图片，其中的参数是图像的路径以及图像的 x 和 y 坐标。在这种情况下，图像和 py 文件在同一个目录中，所以根据相对路径，我们只需要写扩展名为的文件名，如果它在其他目录中，应该使用相关的正确相对路径。

## 蟒蛇 3

```
# drawing a image at the
# specified (x.y) position
pdf.drawInlineImage(image, 130, 400)

# saving the pdf
pdf.save()
```

**下面是完整的程序:**

## 蟒蛇 3

```
# importing modules
from reportlab.pdfgen import canvas
from reportlab.pdfbase.ttfonts import TTFont
from reportlab.pdfbase import pdfmetrics
from reportlab.lib import colors

# initializing variables with values
fileName = 'sample.pdf'
documentTitle = 'sample'
title = 'Technology'
subTitle = 'The largest thing now!!'
textLines = [
    'Technology makes us aware of',
    'the world around us.',
]
image = 'image.jpg'

# creating a pdf object
pdf = canvas.Canvas(fileName)

# setting the title of the document
pdf.setTitle(documentTitle)

# registering a external font in python
pdfmetrics.registerFont(
    TTFont('abc', 'SakBunderan.ttf')
)

# creating the title by setting it's font
# and putting it on the canvas
pdf.setFont('abc', 36)
pdf.drawCentredString(300, 770, title)

# creating the subtitle by setting it's font,
# colour and putting it on the canvas
pdf.setFillColorRGB(0, 0, 255)
pdf.setFont("Courier-Bold", 24)
pdf.drawCentredString(290, 720, subTitle)

# drawing a line
pdf.line(30, 710, 550, 710)

# creating a multiline text using
# textline and for loop
text = pdf.beginText(40, 680)
text.setFont("Courier", 18)
text.setFillColor(colors.red)
for line in textLines:
    text.textLine(line)
pdf.drawText(text)

# drawing a image at the
# specified (x.y) position
pdf.drawInlineImage(image, 130, 400)

# saving the pdf
pdf.save()
```

**输出:**

![](img/7bc6b88c594486c74a823b4214b100ad.png)