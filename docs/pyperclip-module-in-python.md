# Python 中的 Pyperclip 模块

> 原文:[https://www.geeksforgeeks.org/pyperclip-module-in-python/](https://www.geeksforgeeks.org/pyperclip-module-in-python/)

**Pyperclip** 是一个跨平台的 Python 模块，用于复制粘贴剪贴板功能。它适用于 Python 2 和 3。这个模块的创建是为了实现 Python 中的跨平台复制粘贴，这在早期是不存在的。`pyperclip`模块有`copy()`和`paste()`功能，可以向电脑的剪贴板发送文本和从剪贴板接收文本。将程序的输出发送到剪贴板将使它很容易粘贴到电子邮件、文字处理器或其他软件上。

**安装 pyperclip:**

```
pip install pyperclip

```

要将文本复制到剪贴板，将字符串传递给`pyperclip.copy()`。要从剪贴板粘贴文本，调用`pyperclip.paste()`，文本将作为字符串值返回。

**代码 1:**

```
# importing the library
import pyperclip as pc

text1 = "GeeksforGeeks"

# copying text to clipboard
pc.copy(text1)

# pasting the text from clipboard
text2 = pc.paste()

print(text2)
```

**输出:**

```
GeeksforGeeks

```

**代码 2:**

```
# importing the library
import pyperclip as pc

number = 100

# copying text to clipboard
pc.copy(number)

# pasting the text from clipboard
text = pc.paste()

print(text)
print(type(text))
```

**输出:**

```
100

```

**注意:** Copy 函数会将每个数据类型转换为字符串。