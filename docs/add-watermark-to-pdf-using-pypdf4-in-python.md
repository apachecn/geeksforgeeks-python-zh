# 使用 Python 中的 PyPDF4 为 PDF 添加水印

> 原文:[https://www . geesforgeks . org/add-watermark-to-pdf-using-py pdf 4-in-python/](https://www.geeksforgeeks.org/add-watermark-to-pdf-using-pypdf4-in-python/)

我们非常熟悉 pdf(可移植文档格式)最常用的数据格式，带有扩展名. PDF。虽然 PDF 最初是由 Adobe 发明的，但现在由 ISO 维护，用于跨各种操作系统呈现和交换文档。

### 装置

可以使用 **pip** 或 **conda** 安装，具体取决于您使用的是蟒蛇还是蟒蛇。

但是，这是您将如何使用 pip 安装**的具体版本:**

```
pip install PyPDF4==1.27.0

```

否则一般来说:

```
pip install PyPDF4

```

**注意:**兼容 Python、2.7 和 3.2–3.5 版本。

## 添加水印

让我们**给我们的 PDF 文件**添加一个水印(本文的主要目的)。你一定知道水印是在我们的合法文件中主张我们的权利和知识产权的方式，因此它非常重要。

下面是实现。

**原 PDF:**

![](img/9d802b55171fa2fdca1de78d9e89feca.png)

**水印 PDF:**

![](img/0c1b2635df27c81736fe0232b469be04.png)

## 蟒蛇 3

```
# compatible with Python versions 2.6, 2.7,
# and 3.2 - 3.5\. (pip3 install pypdf4)
from PyPDF4 import PdfFileWriter, PdfFileReader
import PyPDF4

PyPDF4.PdfFileReader('GFG.pdf')

def put_watermark(input_pdf, output_pdf, watermark):

    # reads the watermark pdf file through 
    # PdfFileReader
    watermark_instance = PdfFileReader(watermark)

    # fetches the respective page of 
    # watermark(1st page)
    watermark_page = watermark_instance.getPage(0)

    # reads the input pdf file
    pdf_reader = PdfFileReader(input_pdf)

    # It creates a pdf writer object for the
    # output file
    pdf_writer = PdfFileWriter()

    # iterates through the original pdf to
    # merge watermarks
    for page in range(pdf_reader.getNumPages()):

        page = pdf_reader.getPage(page)

        # will overlay the watermark_page on top 
        # of the current page.
        page.mergePage(watermark_page)

        # add that newly merged page to the
        # pdf_writer object.
        pdf_writer.addPage(page)

    with open(output_pdf, 'wb') as out:

        # writes to the respective output_pdf provided
        pdf_writer.write(out)

if __name__ == "__main__":
    put_watermark(
        input_pdf='GFG.pdf',  # the original pdf
        output_pdf='watermark_added1.pdf',  # the modified pdf with watermark
        watermark='geeks.pdf'  # the watermark to be provided
    )
```

**输出:**

![](img/092df25dbe3553bbc8846af26cd1cda7.png)

#### 解释:

1.  **阅读原始输入 pdf 的页面**(使用**pdf 文件阅读器()类**
2.  **阅读**水印**的第一页**(使用 PdfFileReader()类)
3.  使用**pdf writer()类**创建一个 **pdf writer 对象**
4.  接下来，就是在**输入 _pdf 中的页面上重复**。****
5.  **呼叫**。mergePage()** 和**把水印 _page 传给它。****
6.  ****使用 **addPage()** 方法将此**合并页面添加到 pdf writer 对象。**
7.  **使用 **write()方法将其写入**输出页面**。****