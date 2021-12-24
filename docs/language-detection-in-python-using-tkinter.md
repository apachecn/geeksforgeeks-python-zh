# 使用 Tkinter 进行 Python 语言检测

> 原文:[https://www . geesforgeks . org/language-detection-in-python-using-tkinter/](https://www.geeksforgeeks.org/language-detection-in-python-using-tkinter/)

**先决条件:**[Tkit](https://www.geeksforgeeks.org/python-gui-tkinter/)

在本文中，我们将学习在 Tkinter 中使用 Python 进行语言检测。简单地说，语言识别就是确定给定内容使用哪种自然语言的问题。

### 使用的模块

*   **Python 中使用 Tkinter** 模块创建基于 GUI 的界面。
*   对于语言检测，我们将使用[](https://www.geeksforgeeks.org/detect-an-unknown-language-using-python/)****模块。 **langdetect** 模块是谷歌语言检测库的一个端口，支持 55 种语言。这个模块没有 Python 的标准实用程序模块。所以，需要从外部安装。要安装此软件，请在终端中键入以下命令。****

```
**pip install langdetect**
```

*   ****检测到的语言输出是以代码形式出现的，它不显示语言名称。这里我们将使用来自 **iso-639** 模块的**语言**类。该模块用于将语言代码转换为语言名称。要安装，请运行下面给出的命令:****

```
**pip install iso-639**
```

******接近******

*   ****导入模块****
*   ****创建窗口****
*   ****添加按钮****
*   ****添加检测语言的机制****
*   ****添加翻译代码的机制****
*   ****执行代码****

******程序:******

## ****蟒蛇 3****

```
**# Import Module
from tkinter import *
from langdetect import *
from iso639 import languages

# Create Object
root = Tk()

# Set geometry
root.geometry("400x500")

def language_detection():
    text = T.get("1.0", 'end-1c')

    # Get Language code
    language_code = languages.get(alpha2=detect(text))
    l_d.config(text="Language Detected:- "+language_code.name)

# Text Box
T = Text(root)
T.pack()

# label
l_d = Label(root, text="Language Detected:- ")
l_d.pack(pady=10)

# Button
Button(root, text='Detect Language', command=language_detection).pack(pady=10)

# Execute Mainloop
root.mainloop()**
```

******输出:******

****<video class="wp-video-shortcode" id="video-560511-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210218194057/FreeOnlineScreenRecorderProject2.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210218194057/FreeOnlineScreenRecorderProject2.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210218194057/FreeOnlineScreenRecorderProject2.mp4)</video>****