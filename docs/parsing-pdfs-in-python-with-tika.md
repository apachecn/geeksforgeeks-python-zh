# 用 Tika 解析 Python 中的 PDFs】

> 原文:[https://www . geesforgeks . org/parsing-pdfs-in-python-with-tika/](https://www.geeksforgeeks.org/parsing-pdfs-in-python-with-tika/)

Apache Tika 是一个库，用于文档类型检测和从各种文件格式中提取内容。利用这一点，人们可以开发一个通用的类型检测器和内容提取器，从不同类型的文档中提取结构化文本和元数据，例如电子表格、文本文档、图像、PDF，甚至在一定程度上提取多媒体输入格式。Tika-Python 是 Python 绑定到 Apache TikaTM REST 服务，允许用 Python 语言本地调用 Tika。

**安装:**

要安装 Tika，请在终端中键入以下命令。

```
pip install tika

```

**注意:** Tika 是用 Java 写的，所以需要安装一个 java(7 或 7+)运行时

为了从 PDF 文件中提取内容，我们将使用**解析器**对象的 **from_file()** 方法。所以我们先来看看描述。

> **语法:** parser.from_file(filename，additional)
> 
> **参数:**
> 
> *   [T0】 filename: 【T1] This is the location of the file. It is opened in rb mode, that is, read binary mode.
> *   [t0 T0】 additional: param service: the service requested from tika server, with the default value of "all", which leads to recursive text content+metadata.
>     *   Meta only returns metadata. "text" only returns the content.
>     *   Param xmlContent: can have XML content, default value -False.
> 
> **返回类型:**字典。

现在，让我们看看用于提取 pdf 数据的 python 程序:

**示例 1:** 提取 pdf 文件的内容。

## 蟒 3

```
# import parser object from tike
from tika import parser  

# opening pdf file
parsed_pdf = parser.from_file("sample.pdf")

# saving content of pdf
# you can also bring text only, by parsed_pdf['text'] 
# parsed_pdf['content'] returns string 
data = parsed_pdf['content'] 

# Printing of content 
print(data)

# <class 'str'>
print(type(data))
```