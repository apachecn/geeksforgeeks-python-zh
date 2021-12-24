# 使用 Python 将 PDF 文件文本转换为音频语音

> 原文:[https://www . geesforgeks . org/convert-pdf-file-text-to-audio-speech-use-python/](https://www.geeksforgeeks.org/convert-pdf-file-text-to-audio-speech-using-python/)

让我们看看如何阅读一个把文本文件转换成音频的 PDF。

使用的包:

*   **pyttsx3:** 是一个文本到语音的 Python 库。它有许多功能，有助于机器与我们交流。这将有助于机器对我们说话
*   **PyPDF2:** 这将有助于从 PDF 中提取文本。作为 PDF 工具包构建的纯 Python 库。它能够提取文档信息，逐页拆分文档，逐页合并文档等。

这两个模块都需要安装

```py
pip install pyttsx3
pip install PyPDF2

```

您还需要了解 [**open()**](https://www.geeksforgeeks.org/file-handling-python/) 功能，该功能将帮助我们以阅读模式打开 PDF。也推荐关于 OOPS 概念的知识。

下面是示例中读取的 PDF 的链接:[https://drive . Google . com/file/d/1z hf7-_ v6CVUtgd _ xmk 562mg 6 ciewi 1 QR/view？usp =共享](https://drive.google.com/file/d/1zhf7-_v6CVUtgd_XMK562mg6ciewi1QR/view?usp=sharing)

**进场:**

*   导入 PyPDF2 和 pyttx3 模块。
*   打开 PDF 文件。
*   使用**PDF 文件阅读器()**读取 PDF 文件。我们只需要给出 PDF 的路径作为参数。
*   使用 **getPage()** 方法选择要读取的页面。
*   使用**提取文本()**从页面中提取文本。
*   实例化 pyttx3 对象。
*   使用 **say()** 和 **runwait()方法**朗读课文。

这是它的代码

## 蟒蛇 3

```py
# importing the modules
import PyPDF2
import pyttsx3

# path of the PDF file
path = open('file.pdf', 'rb')

# creating a PdfFileReader object
pdfReader = PyPDF2.PdfFileReader(path)

# the page with which you want to start
# this will read the page of 25th page.
from_page = pdfReader.getPage(24)

# extracting the text from the PDF
text = from_page.extractText()

# reading the text
speak = pyttsx3.init()
speak.say(text)
speak.runAndWait()
```

**输出:**

<video class="wp-video-shortcode" id="video-497473-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20201006164050/Newgfgvedio.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20201006164050/Newgfgvedio.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20201006164050/Newgfgvedio.mp4)</video>