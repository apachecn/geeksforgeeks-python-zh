# Python–使用 Pyperclip 模块

将简单行转换为项目符号行

> 原文:[https://www . geeksforgeeks . org/python-convert-simple-line-to-bullets-line-使用-pyperclip-module/](https://www.geeksforgeeks.org/python-convert-simple-lines-to-bulleted-lines-using-the-pyperclip-module/)

**Pyperclip** 是跨平台的 Python 模块，用于将文本复制粘贴到剪贴板。假设您想自动完成复制文本的任务，然后将它们转换为项目符号点。这可以使用`pyperclip`模块来完成。为了更好地理解，请考虑以下示例。

**示例:**

> **剪贴板内容:**
> 团结我们就站，分裂我们就倒。
> 有志者事竟成。
> 罗马不是一天建成的。
> 
> **新剪贴板内容:**
> *团结我们站，分裂我们倒。
> *有志者事竟成。
> *罗马不是一天建成的。

**方法:**首先，你需要复制任何你想转换成项目符号文本的文本，然后你需要运行程序，在它成功执行后，当你粘贴剪贴板的内容时，你可以看到内容已经被修改。该模块使用了两种方法，即`paste()`方法用于粘贴并返回复制的字符串，以及`copy()`方法用于将字符串传递到剪贴板。

下面是实现。

```py
import pyperclip

# saves text copied to clipboard
# in variable text
text = pyperclip.paste()
print("Before Modification:")
print(text)

# stores different lines of text
# in a list named lines
lines = text.split("\n")

# adds * to every line stored
# in list
for i in range(len(lines)):
    lines[i] = "*" + lines[i]

# converts the list of different
# lines to single text
text = "\n".join(lines)

# copies new modified text
# to the clipboard
pyperclip.copy(text)
print("\nAfter Modification:") 
print(pyperclip.paste())
```

**Output:**

```py
Before Modification:
United we stand, divided we fall.
Where there is a will, there is a way.
Rome was not built in a day.

After Modification:
*United we stand, divided we fall.
*Where there is a will, there is a way.
*Rome was not built in a day.

```