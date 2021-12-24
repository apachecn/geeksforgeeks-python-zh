# 使用 Python 构建一个从 PDF 中提取网址和元数据的应用程序

> 原文:[https://www . geesforgeks . org/build-a-application-to-extract-URL-and-metadata-from-a-pdf-use-python/](https://www.geeksforgeeks.org/build-an-application-to-extract-url-and-metadata-from-a-pdf-using-python/)

PDF(可移植文档格式)是 Adobe 开发的最常用的独立于平台的文件格式，用于呈现文档。Python 有很多 PDF 相关的包，其中之一就是 *pdfx* 模块。*PDF FX*模块用于从给定的 PDF 或 PDF 网址中提取网址、元数据和纯文本。

**功能:**

*   Extract references and metadata from a given PDF.
*   Check pdf, URL, arxiv and DOI references.
*   Download all referenced pdfs quickly and in parallel.
*   Check the broken links (use the -c flag).
*   Output is text or JSON (use the -j flag).
*   Extract PDF text (use the–text flag).
*   Use command line tools or Python packages.
*   Compatible with Python 2 and 3.
*   Suitable for local and online pdf.

### **入门:**

首先，我们需要安装 *pdfx* 模块，在终端运行下面的代码。

```py
pip install pdfx
```

**方法:**

*   Import *pdfx* module.
*   Use *PDFx to read pdf files. Pdfx ()* method.
*   Use *get _ metadata ()* method to get metadata.
*   用 *Get _ references _ as _ dict()* 方法获取网址.

**实施:**

**第一步:**导入模块，读取 PDF 文件。

## 蟒 3

```py
# import module
import pdfx

# reading pdf file
pdf = pdfx.PDFx("geeksforgeeks.pdf")

# display
print(pdf)
```

**输出:**

```py
<pdfx.PDFx at 0x1c189244a88>
```

意思是 *pdfx。PDFx* 对象创建于 *0x1c189244a88* 你记忆中的这个位置。

**第二步:**从 PDF 获取元数据。

## 蟒 3

```py
pdf.get_metadata()
```