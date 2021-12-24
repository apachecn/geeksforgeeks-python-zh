# 使用 Python 确定文件格式

> 原文:[https://www . geesforgeks . org/decision-file-format-use-python/](https://www.geeksforgeeks.org/determining-file-format-using-python/)

识别文件类型的一般方法是查看其扩展名。但通常情况并非如此。这种通过将扩展名与文件类型相关联来识别文件的标准由一些操作系统家族(主要是 Windows)强制实施。其他操作系统如 Linux(及其变体)使用*魔法数字* r 来识别文件类型。一**幻数***T5】是一个常量值，用于一个文件的识别。这种方法在命名文件时提供了更大的灵活性，并且不要求存在扩展名。幻数有利于识别文件，因为有时文件可能没有正确的文件扩展名(或者根本没有扩展名)。*

在本文中，我们将学习如何使用 python 通过文件的扩展名来识别文件。我们将使用 [**Python 魔法库**](https://github.com/ahupp/python-magic) 为我们的程序提供这样的功能。要安装库，请在操作系统的命令解释器中执行以下命令

```py
pip install python-magic

```

出于演示目的，我们将使用文件名 a*pple.jpg*，其内容如下:-

![](img/4e15b81111b94c6293d11e5e691d8b3f.png)

从内容上看，该文件是一个 HTML 文件。但是由于它是用. jpg 扩展名保存的，操作系统将无法识别它的实际文件类型。所以这个文件适合我们的项目。

## 蟒蛇 3

```py
import magic

# printing the human readable type of the file
print(magic.from_file('apple.jpg'))

# printing the mime type of the file
print(magic.from_file('apple.jpg', mime = True))
```

**输出:**

```py
HTML document, ASCII text, with CRLF line terminators
text/html

```

**说明:**

首先我们导入*魔法*库。然后我们使用 *magic.from_file()* 方法获得人类可读的文件类型。之后我们使用 *mime=True* 属性来获得文件的 mime 类型。

**使用上述代码时需要考虑的事项:**

*   该代码在 Linux 和 Mac 操作系统上工作。但是在这些操作系统上有一个名为*文件*的内置终端命令，它提供了与这个程序相同的功能，而不需要安装任何其他库。
*   使用*扩展名*的文件类型识别也存在于库的较新版本中。
*   由于文件类型识别通常是通过文件头的指纹查找来进行的，因此并不强制要求加载整个文件进行类型识别。也可以使用 *magic.from_buffer()* 提供文件的小部分作为参数，并使用 *open('file.ext '，' rb ')传递文件的初始字节。read(n)* (仅在了解文件类型的头格式时推荐)。