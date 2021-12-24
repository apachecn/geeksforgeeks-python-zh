# 将 Python 中的 Unicode 转换为 ASCII

> 原文:[https://www . geeksforgeeks . org/convert-unicode-ascii-in-python/](https://www.geeksforgeeks.org/convert-unicode-to-ascii-in-python/)

**Unicode** 是通用字符集，是支持全球所有语言的标准。它包含 150 多个脚本使用的 140，000 多个字符以及各种符号。 **ASCII** 另一方面是 Unicode 的一个子集，也是最兼容的字符集，由 128 个英文字母、数字和标点组成，剩下的是控制字符。本文讨论了使用 Python 库 **anyascii** 将各种 Unicode 字符转换为更简单的 ASCII 表示。

文本从一个字符转换成另一个字符。每个脚本的映射都基于传统的方案。符号字符根据其含义或外观进行转换。如果输入包含 ASCII 字符，它们是不变的，其余的都尝试转换为 ASCII。未知字符被删除。

### **安装:**

要安装此模块，请在终端中键入以下命令。

```
pip install anyascii
```

**示例 1:使用多种语言**

在这种情况下，像 Unicode 这样的各种不同的语言被设置为输入，输出被给出为转换后的 ASCII 字符。

## 蟒 3

```
from anyascii import anyascii

# checking for Hindi script
hindi_uni = anyascii('नमस्ते विद्यार्थी')

print("The translation from hindi Script : "
      + str(hindi_uni))

# checking for Punjabi script
pun_uni = anyascii('ਸਤਿ ਸ੍ਰੀ ਅਕਾਲ')

print("The translation from Punjabi Script : "
      + str(pun_uni))
```

**输出:**

```
The translation from hindi Script : nmste vidyarthi
The translation from Punjabi Script : sti sri akal
```

**示例 2:使用 Unicode 表情符号**

这个库还处理表情符号和符号的工作，它们通常是 Unicode 表示。

```
from anyascii import anyascii

# working with emoji example
emoji_uni = anyascii('😎 👑 🍎')

print("The ASCII from emojis : "
      + str(emoji_uni))

# checking for Symbols
sym_uni = anyascii('➕ ☆ ℳ')

print("The ASCII from Symbols : "
      + str(sym_uni))
```

**输出:**

```
The ASCII from emojis : :sunglasses: :crown: :apple:
The ASCII from Symbols : :heavy_plus_sign: * M
```