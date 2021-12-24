# 如何在 Python 中暴力破解 ZIP 文件密码？

> 原文:[https://www . geeksforgeeks . org/如何在 python 中使用蛮力-zip-file-passwords/](https://www.geeksforgeeks.org/how-to-brute-force-zip-file-passwords-in-python/)

在本文中，我们将看到一个 Python 程序，它将使用暴力破解 zip 文件的密码。

ZIP 文件格式是一种常见的归档和压缩标准。它用于压缩文件。有时候，压缩文件是保密的，所有者不想让每个人都能访问。因此，zip 文件受密码保护。如果密码很常见，那么它很容易被破解。在这里，我们将使用暴力破解 zip 文件的密码。

强力方法是一种使用一组预定义值破解密码直到成功的方法。这基本上是一种“试一试”的方法。如果值集很高，这种方法可能需要很长时间，但它的成功率很高。数值越多，破解密码的几率就越大。在这里，我们将使用大小为 133 兆字节的“rockyou”文本文件和超过 1400 万组密码来尝试。在这里下载文本文件[。](https://github.com/brannondorsey/naive-hashcat/releases/download/data/rockyou.txt)

**进场:**

*   首先，导入 [zipfile](https://docs.python.org/3/library/zipfile.html) 模块。
*   初始化 ZipFile 对象，这有助于提取 zip 文件的内容。
*   统计“rockyou.txt”文件中出现的单词数，并将其显示在终端上。
*   调用“破解密码”函数，如果找到密码则返回真，否则返回假。将文本文件和 ZipFile 对象的名称作为参数传递。
*   idx 变量用于跟踪行号。
*   以“rb”模式打开文本文件“rockyou.txt”，以便以二进制形式处理文件内容。这是因为文件中包含一些特殊符号，如果在“r”模式下打开文件，这些符号是无法处理的，会产生**unicodedecodererror**。
*   打开文件后，从文件中提取该行，然后从中拆分单词。
*   在 try 块中，通过向 extractall 方法的 pwd 字段提供密码来提取 zip 文件的内容。 **extractall()** 方法将 zip 文件的所有内容提取到当前工作目录。上面的程序在与这个 python 脚本相同的目录中提取了一个名为“gfg.zip”的 zip 文件。
*   如果密码不正确，将生成一个异常。在除块中，继续循环检查文件中的其他单词。
*   如果找到密码，返回真，否则最后返回假，并显示所需的消息。

**以下是完整实现:**

## 蟒蛇 3

```py
import zipfile

def crack_password(password_list, obj):
    # tracking line no. at which password is found
    idx = 0

    # open file in read byte mode only as "rockyou.txt"
    # file contains some special characters and hence
    # UnicodeDecodeError will be generated
    with open(password_list, 'rb') as file:
        for line in file:
            for word in line.split():
                try:
                    idx += 1
                    obj.extractall(pwd=word)
                    print("Password found at line", idx)
                    print("Password is", word.decode())
                    return True
                except:
                    continue
    return False

password_list = "rockyou.txt"

zip_file = "gfg.zip"

# ZipFile object initialised
obj = zipfile.ZipFile(zip_file)

# count of number of words present in file
cnt = len(list(open(password_list, "rb")))

print("There are total", cnt,
      "number of passwords to test")

if crack_password(password_list, obj) == False:
    print("Password not found in this file")
```

**输出:**

![](img/e835ace533883b3e3730d0019c3a204d.png)