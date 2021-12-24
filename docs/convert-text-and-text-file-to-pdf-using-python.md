# 使用 Python 将文本和文本文件转换为 PDF

> 原文:[https://www . geesforgeks . org/convert-text-and-text-file-to-pdf-using-python/](https://www.geeksforgeeks.org/convert-text-and-text-file-to-pdf-using-python/)

pdf 是最重要、应用最广泛的数字媒体之一。PDF 代表**便携文档格式**。它使用。pdf 扩展名。它用于可靠地呈现和交换文档，独立于软件、硬件或操作系统。将给定的文本或文本文件转换为 PDF(可移植文档格式)是我们在现实生活中进行的各种项目的基本要求之一。所以，如果你不知道如何把给定的文本转换成 PDF，那么这篇文章就是为你准备的。在本文中，您将了解在 Python 中将文本和文本文件转换为 PDF 的方法。
**FPDF** 是一个 Python 类，允许用 Python 代码生成 PDF 文件。它是免费使用的，不需要任何 API 密钥。FPDF 代表免费 PDF。这意味着任何一种修改都可以在 PDF 文件中完成。
**这个职业的主要特点是:**

*   易于使用

*   它允许页面格式和边距

*   它允许管理页眉和页脚

*   Python 2.5 到 3.7 支持

*   Unicode (UTF-8) TrueType 字体子集嵌入

*   条码 I2of5 和码 39，二维码快到了……

*   PNG、GIF 和 JPG 支持(包括透明度和 alpha 通道)

*   带有视觉设计器和基本 html2pdf 的模板

*   异常支持、其他小修复、改进和 PEP8 代码清理

要安装 fpdf 模块，请在终端中键入以下命令。

```
pip install fpdf
```

**进场:**

1.  从 fpdf 模块
    导入 FPDF 类
2.  增加一页

3.  设置字体

4.  插入一个单元格并提供文本

5.  用“”保存 pdf。pdf " extension

**例:**

## 蟒蛇 3

```
# Python program to create
# a pdf file

from fpdf import FPDF

# save FPDF() class into a
# variable pdf
pdf = FPDF()

# Add a page
pdf.add_page()

# set style and size of font
# that you want in the pdf
pdf.set_font("Arial", size = 15)

# create a cell
pdf.cell(200, 10, txt = "GeeksforGeeks",
         ln = 1, align = 'C')

# add another cell
pdf.cell(200, 10, txt = "A Computer Science portal for geeks.",
         ln = 2, align = 'C')

# save the pdf with name .pdf
pdf.output("GFG.pdf")  
```

**输出:**

![python fpdf](img/96ed618ce074f2d6eb9b1867fa676b84.png)

#### 将文本文件转换为 PDF

现在，如果我们想使上述程序更先进，我们可以做的是，从一个给定的文本文件提取数据使用文件处理，然后将其插入 pdf 文件。方法同上，你必须做的一件事是使用文件处理从文本文件中提取数据。
**注:**参考[本文](https://www.geeksforgeeks.org/file-handling-python/)了解更多 Python 中的文件处理。
**示例:**假设文本文件如下–

![python-fpdf-text-file](img/0823863b59abfdf2980a1620fb6253fd.png)

## 蟒蛇 3

```
# Python program to convert
# text file to pdf file

from fpdf import FPDF

# save FPDF() class into
# a variable pdf
pdf = FPDF()  

# Add a page
pdf.add_page()

# set style and size of font
# that you want in the pdf
pdf.set_font("Arial", size = 15)

# open the text file in read mode
f = open("myfile.txt", "r")

# insert the texts in pdf
for x in f:
    pdf.cell(200, 10, txt = x, ln = 1, align = 'C')

# save the pdf with name .pdf
pdf.output("mygfg.pdf")  
```

**输出:**

![python-fpdf](img/c9679a2ded1d36ae102df636ed7642aa.png)