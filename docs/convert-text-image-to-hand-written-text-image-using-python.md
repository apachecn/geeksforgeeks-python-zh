# 使用 Python 将文本图像转换为手写文本图像

> 原文:[https://www . geesforgeks . org/convert-text-image-to-hand-write-text-image-use-python/](https://www.geeksforgeeks.org/convert-text-image-to-hand-written-text-image-using-python/)

在本文中，我们将看到如何使用 Python 中的 PyWhatkit、抱枕和 Tesseract 将文本图像转换为手写文本图像。

### 所需模块:

**小魔方:**有时被称为**Python-小魔方**，是一个基于 Python 的光学字符识别( **OCR** )程序。它可以读取和识别照片、车牌和其他文档中的文本。为了解释提供的图片中的单词，我们将使用宇宙魔方软件。

```py
pip install pytesseract
```

**Pywhatkit:** 它是一个可以用于各种事情的库，包括发送 WhatsApp 消息、观看 YouTube 视频、搜索 Google 以及书写手写文本。

```py
pip install pywhatkit
```

[**【枕头】**](https://www.geeksforgeeks.org/python-pillow-a-fork-of-pil/) **:** 这个模块增加了更多的功能，在各大操作系统上运行，并且有 Python 3 的支持。它支持多种图像格式，包括“jpeg”、“png”、“bmp”、“gif”、“ppm”和“tiff”。有了枕头模块，你几乎可以用数码照片做任何事情。

```py
pip install Pillow
```

**注:**参观安装 [**宇宙魔方**](https://github.com/UB-Mannheim/tesseract/wiki)；向下滚动查找 **32 位**和 **64 位**系统的最新安装程序；根据需要下载它们。

### 逐步实施:

**步骤 1:** 导入以下模块。

## 蟒 3

```py
import pytesseract 
from PIL import Image 
import os
import pywhatkit as kit
```

**第二步:**导航到图片所在的路径，可以使用 **OS** 模块中的 **chdir** 功能更改目录。

## 蟒 3

```py
os.chdir(r"C:\Users\Dell\Downloads")
```

**第三步:**复制宇宙魔方的安装路径，粘贴在这里，或者验证宇宙魔方的目录，复制整个路径。

## 蟒 3

```py
pytesseract.pytesseract.tesseract_cmd = r"C:\Users\Dell\AppData\Local\/
Tesseract-OCR\tesseract.exe"
```