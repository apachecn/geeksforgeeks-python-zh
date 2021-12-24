# 使用 Python 检测未知语言

> 原文:[https://www . geesforgeks . org/detect-一种未知语言-使用-python/](https://www.geeksforgeeks.org/detect-an-unknown-language-using-python/)

语言检测背后的思想是基于对文本中的表达和单词中的字符的检测。主要原理是检测英语中的常用词，如 to、of。Python 为语言检测提供了各种模块。在本文中，涵盖的模块有:

*   langdetect
*   textblob
*   康利德

**方法 1:** 使用`langdetect`库

这个模块是谷歌语言检测库的一个端口，支持 55 种语言。这个模块没有 Python 的标准实用程序模块。所以，需要从外部安装。要安装此软件，请在终端中键入以下命令。

```
pip install langdetect
```

```
# Python program to demonstrate
# langdetect

from langdetect import detect

# Specifying the language for
# detection
print(detect("Geeksforgeeks is a computer science portal for geeks"))
print(detect("Geeksforgeeks - это компьютерный портал для гиков"))
print(detect("Geeksforgeeks es un portal informático para geeks"))
print(detect("Geeksforgeeks 是面向极客的计算机科学门户"))
print(detect("Geeksforgeeks geeks के लिए एक कंप्यूटर विज्ञान पोर्टल है"))
print(detect("Geeksforgeeksは、ギーク向けのコンピューターサイエンスポータルです。"))
```

**输出:**

```
en
ru
es
no
hi
ja

```

**方法 2:** 使用`textblob`库

该模块用于自然语言处理任务，如名词短语提取、情感分析、分类、翻译等。要安装此模块，请在终端中键入以下命令。
('ru '，-48860 . 88888888861

```
pip install textblob
```

**示例:**

```
# Python program to demonstrate
# textblob

from textblob import TextBlob

L = ["Geeksforgeeks is a computer science portal for geeks",
    "Geeksforgeeks - это компьютерный портал для гиков",
    "Geeksforgeeks es un portal informático para geeks",
    "Geeksforgeeks 是面向极客的计算机科学门户",
    "Geeksforgeeks geeks के लिए एक कंप्यूटर विज्ञान पोर्टल है",
    "Geeksforgeeksは、ギーク向けのコンピューターサイエンスポータルです。",
    ]

for i in L:

    # Language Detection
    lang = TextBlob(i) 
    print(lang.detect_language())
```

**输出:**

```
en
ru
es
zh-CN
hi
ja

```

**方法 3:** 使用`langrid`库

该模块是一个独立的语言识别工具。它经过大量语言(目前为 97 种)的预先培训。它是一个依赖关系最小的. py 文件。要安装此软件，请在终端中键入以下命令。

```
pip install langrid
```

**示例:**

```
# Python program to demonstrate
# langid

import langid

L = ["Geeksforgeeks is a computer science portal for geeks",
    "Geeksforgeeks - это компьютерный портал для гиков",
    "Geeksforgeeks es un portal informático para geeks",
    "Geeksforgeeks 是面向极客的计算机科学门户",
    "Geeksforgeeks geeks के लिए एक कंप्यूटर विज्ञान पोर्टल है",
    "Geeksforgeeksは、ギーク向けのコンピューターサイエンスポータルです。",
    ]

for i in L:

    # Language detection
    print(langid.classify(i))
```

**输出:**

```
('en', -119.93012762069702)
('ru', -641.3409600257874)
('es', -191.01083326339722)
('zh', -199.18277835845947)
('hi', -286.99300467967987)
('ja', -875.6610476970673)

```