# 使用 Python 创建一个空文件

> 原文:[https://www . geeksforgeeks . org/create-a-empty-python/](https://www.geeksforgeeks.org/create-an-empty-file-using-python/)

对于任何程序员来说，文件处理都是一个非常重要的概念。它可用于创建、删除、移动文件或存储应用程序数据、用户配置、视频、图像等。Python 也支持文件处理，并允许用户处理文件，即读写文件，以及许多其他文件处理选项，对文件进行操作。

> 请参考以下文章来了解文件处理的基础知识。
> 
> *   [文件处理基础](https://www.geeksforgeeks.org/file-handling-python/)
> *   [读写文件](https://www.geeksforgeeks.org/reading-writing-text-files-python/)

## 创建空文件

文件处理也可以用于创建文件。甚至像`.pdf`、`.txt`、`.jpeg`这样不同扩展名的文件都可以使用 Python 中的文件处理来创建。要创建文件，必须打开文件进行写入。要打开文件进行写入[文件的访问模式](https://www.geeksforgeeks.org/reading-writing-text-files-python/)必须是 **w** 、 **a** 、 **w+** 、 **a+** 。[访问模式](https://www.geeksforgeeks.org/reading-writing-text-files-python/)控制打开文件中可能的操作类型。它指的是文件打开后将如何使用。以下是创建空文件的访问模式列表。

*   **只写(' w'):** 打开文件写。对于现有文件，数据会被截断和覆盖。
*   **读写(' w+'):** 打开文件进行读写。对于现有文件，数据会被截断和覆盖。
*   **仅追加(' a'):** 打开文件进行写入。正在写入的数据将被插入到现有数据的末尾。
*   **追加并读取(' a+'):** 打开文件进行读写。正在写入的数据将被插入到现有数据的末尾。

**注意:**如果没有指定路径，则在脚本的同一目录下创建文件。

**示例#1:** 在此示例中，我们将创建一个新文件 myfile.txt。为了验证这一点，我们将使用 [os](https://www.geeksforgeeks.org/os-module-python-examples/) 模块的`[os.listdir()](https://www.geeksforgeeks.org/python-os-listdir-method/)`方法列出创建新文件前后的目录。

```py
# Python program to demonstrate
# creating a new file

# importing module
import os

# path of the current script
path = 'D:/Pycharm projects/gfg'

# Before creating
dir_list = os.listdir(path) 
print("List of directories and files before creation:")
print(dir_list)
print()

# Creates a new file
with open('myfile.txt', 'w') as fp:
    pass
    # To write data to new file uncomment
    # this fp.write("New file created")

# After creating 
dir_list = os.listdir(path)
print("List of directories and files after creation:")
print(dir_list)
```

**输出:**

```py
List of directories and files before creation:
['.idea', 'gfg.py', 'venv']

List of directories and files after creation:
['.idea', 'gfg.py', 'myfile.txt', 'venv']

```

**#示例 2:** 在指定位置创建新文件。使用[操作系统模块](https://www.geeksforgeeks.org/os-module-python-examples/)在指定位置创建文件。下面是实现。

```py
# Python program to demonstrate
# creation of new file

import os

# Specify the path
path = 'D:/Pycharm projects/GeeksforGeeks/Nikhil'

# Specify the file name
file = 'myfile.txt'

# Before creating
dir_list = os.listdir(path) 
print("List of directories and files before creation:")
print(dir_list)
print()

# Creating a file at specified location
with open(os.path.join(path, file), 'w') as fp:
    pass
    # To write data to new file uncomment
    # this fp.write("New file created")

# After creating 
dir_list = os.listdir(path)
print("List of directories and files after creation:")
print(dir_list)
```

**输出:**

```py
List of directories and files before creation:
['test_nikhil.txt']

List of directories and files after creation:
['myfile.txt', 'test_nikhil.txt']

```