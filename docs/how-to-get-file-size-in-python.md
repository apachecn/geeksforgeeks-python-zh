# 如何在 Python 中获取文件大小？

> 原文:[https://www . geesforgeks . org/如何获取 python 中的文件大小/](https://www.geeksforgeeks.org/how-to-get-file-size-in-python/)

我们可以使用不同的方法来获得 Python 中的文件大小。在 Python 中获取文件大小以监控文件大小很重要，或者在根据文件大小对目录中的文件进行排序的情况下也很重要。

**方法 1:** 使用[模块的 *getsize* 功能](https://www.geeksforgeeks.org/os-path-module-python/)

该函数以文件路径作为参数，并返回文件大小(字节)。

**示例:**

## 蟒蛇 3

```
# approach 1
# using getsize function os.path module
import os

file_size = os.path.getsize('d:/file.jpg')
print("File Size is :", file_size, "bytes")
```

**输出:**

```
File Size is : 218 bytes
```

**方法 2:** 使用操作系统模块的 *stat* 功能

此函数将文件路径作为参数(字符串或文件对象)，并返回作为输入给出的文件路径的统计详细信息。

**示例:**

## 蟒蛇 3

```
# approach 2
# using stat function of os module
import os

file_size = os.stat('d:/file.jpg')
print("Size of file :", file_size.st_size, "bytes")
```

**输出:**

```
Size of file : 218 bytes
```

**方法 3:** 使用文件对象

要获取文件大小，请按照下列步骤操作–

1.  使用*打开*功能打开文件，并将返回的对象存储在变量中。打开文件时，光标指向文件的开头。
2.  文件对象有*寻道*方法，用于将光标设置到所需位置。它接受两个参数-开始位置和结束位置。要将光标设置在文件的结束位置，请使用方法 *os。SEEK_END。*
3.  文件对象有*告诉*方法，可以用来获得当前光标位置，这将相当于光标已经移动的字节数。所以这个方法实际上以字节为单位返回文件的大小。

**示例:**

## 蟒蛇 3

```
# approach 3
# using file object

# open file
file = open('d:/file.jpg')

# get the cursor positioned at end
file.seek(0, os.SEEK_END)

# get the current position of cursor
# this will be equivalent to size of file
print("Size of file is :", file.tell(), "bytes")
```

**输出:**

```
Size of file is : 218 bytes
```

**方法 4:** 使用路径库模块

Path 对象的 stat()方法返回 st_mode、st_dev 等。文件的属性。stat 方法的 st_size 属性以字节为单位给出文件大小。

**示例:**

## 蟒蛇 3

```
# approach 4
# using pathlib module
from pathlib import Path

# open file
Path(r'd:/file.jpg').stat()

# getting file size
file=Path(r'd:/file.jpg').stat().st_size

# display the size of the file
print("Size of file is :", file, "bytes")

# this code was contributed by debrc
```

**输出:**

```
Size of file is : 218 bytes
```