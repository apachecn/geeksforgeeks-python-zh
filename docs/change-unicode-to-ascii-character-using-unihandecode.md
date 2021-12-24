# 使用单键代码

将 Unicode 更改为 ASCII 字符

> 原文:[https://www . geeksforgeeks . org/change-unicode 到 ascii-character-using-unihandecode/](https://www.geeksforgeeks.org/change-unicode-to-ascii-character-using-unihandecode/)

Unicode 通常被表示为“\u4EB0\U5317”，但是这对于真正想要阅读文本内容的用户来说几乎是无用的。因此，在本文中，我们将看到如何使用 Unihandecode 模块将 Unicode 转换为 ASCII 字符。

## **什么是 Unihandecode？**

Unihandecode 提供了一个函数“decode (……”)，它将 Unicode 数据作为输入，并试图用 ASCII 字符表示它。用简单的语言，我们可以说，将 Unicode 中的所有字符转换为 ASCII 字母是一种音译。

解码器列表

*   **‘ja’:**日语汉字、平假名和片假名。
*   **‘zh’:**汉字
*   **'kr':** 韩文字符
*   **“VN”:**越南语字符

### **安装**

这个模块没有内置 Python。要安装此软件，请在终端中键入以下命令。

```py
pip install unihandecode 
```

**例:**

## 蟒 3

```py
from unihandecode import Unihandecoder

data1 = Unihandecoder(lang='zh')
print(data1.decode("\u660e\u5929\u7684\u98ce\u5439"))
```

**输出:**

```py
Ming Tian De Feng Chui

```

第一行参数采用您想要使用的解码器的名称。然后，解码器将字符串作为参数，并返回音译字符串。