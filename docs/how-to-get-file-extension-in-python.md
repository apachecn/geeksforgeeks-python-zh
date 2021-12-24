# 如何在 Python 中获取文件扩展名？

> 原文:[https://www . geesforgeks . org/如何获取 python 中的文件扩展名/](https://www.geeksforgeeks.org/how-to-get-file-extension-in-python/)

在 Python 中，我们可以使用下面讨论的两种不同方法提取文件扩展名–

**方法 1:** 使用 Python os 模块 [splitext()](https://www.geeksforgeeks.org/python-os-path-splitext-method/) 功能

该函数将文件路径字符串拆分为文件名和文件扩展名，形成一对根和扩展名，这样当两者都添加时，我们就可以再次检索文件路径(file_name +扩展名= path)。当操作系统模块已经在使用时**，优先使用该功能。**

**示例:**

## 蟒蛇 3

```
import os

# this will return a tuple of root and extension
split_tup = os.path.splitext('my_file.txt')
print(split_tup)

# extract the file name and extension
file_name = split_tup[0]
file_extension = split_tup[1]

print("File Name: ", file_name)
print("File Extension: ", file_extension)
```

**输出:**

```
('my_file', '.txt')
File Name:  my_file
File Extension:  .txt
```

**方法 2:** 使用[路径库](https://www.geeksforgeeks.org/pathlib-module-in-python/)模块

pathlib。路径()。Pathlib 模块的后缀方法可以用来提取文件路径的扩展名。这种方法是面向对象方法的首选。

**示例:**

## 蟒蛇 3

```
import pathlib

# function to return the file extension
file_extension = pathlib.Path('my_file.txt').suffix
print("File Extension: ", file_extension)
```

**输出:**

```
File Extension:  .txt
```