# Python–检查文件或目录是否存在

> 原文:[https://www . geesforgeks . org/python-检查文件或目录是否存在/](https://www.geeksforgeeks.org/python-check-if-a-file-or-directory-exists/)

有时，检查目录或文件是否存在的需要变得很重要，因为您可能希望防止覆盖已经存在的文件，或者您可能希望在加载文件之前确保该文件可用或不可用。
有多种方法可以检查文件或目录是否已经存在。它们是–

*   [使用 os.path.exists()](#exists)
*   [使用 os.path.isfile()](#isfile)
*   [使用 os.path.isdir()](#isdir)
*   [使用路径库。](#pathlib)

## 使用 os.path.exists()

**Python 中的 OS 模块**提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。 **os.path** 模块是 Python 中 **OS 模块**的子模块，用于常用路径名操作。
**注意:**要了解更多关于 OS 模块[的信息，请点击此处](https://www.geeksforgeeks.org/os-module-python-examples/)。
Python 中的 os.path.exists()方法用于检查指定路径是否存在。这个方法也可以用来检查给定的路径是否引用了打开的文件描述符。

> **语法:** os.path.exists(路径)
> **参数:**
> **路径:**表示文件系统路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **返回类型:**该方法返回 bool 类的布尔值。如果路径存在，此方法返回真，否则返回假。

**示例:**

## 蟒蛇 3

```py
# Python program to explain os.path.exists() method 

# importing os module 
import os

# Specify path
path = '/usr/local/bin/'

# Check whether the specified
# path exists or not
isExist = os.path.exists(path)
print(isExist)

# Specify path
path = '/home/User/Desktop/file.txt'

# Check whether the specified
# path exists or not
isExist = os.path.exists(path)
print(isExist)
```

**输出:**

```py
True
False
```

## 使用 os.path.isfile()

Python 中的 os.path.isfile()方法用于检查指定路径是否为现有的常规文件。

> **语法:** os.path.isfile(路径)
> **参数:**
> **路径:**表示文件系统路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> **返回类型:**该方法返回 bool 类的布尔值。如果指定的路径是现有的常规文件，此方法返回 True，否则返回 False。

**示例:**

## 蟒蛇 3

```py
# Python program to explain os.path.isfile() method

# importing os module 
import os

# Path
path = 'C:/Users/gfg/Desktop/file.txt'

# Check whether the 
# specified path is 
# an existing file
isFile = os.path.isfile(path)
print(isFile)

# Path
path = '/home/User/Desktop/'

# Check whether the 
# specified path is 
# an existing file
isFile = os.path.isfile(path)
print(isFile)
```

**输出:**

```py
True
False
```

## 使用 os.path.isdir()

Python 中的 os.path.isdir()方法用于检查指定路径是否为现有目录。此方法遵循符号链接，这意味着如果指定的路径是指向目录的符号链接，则该方法将返回 True。

> **语法:** os.path.isdir(路径)
> **参数:**
> **路径:**表示文件系统路径的类路径对象。
> **返回类型:**该方法返回 bool 类的布尔值。如果指定的路径是现有目录，此方法返回 True，否则返回 False。

**例:**

## 蟒蛇 3

```py
# Python program to explain os.path.isdir() method 

# importing os.path module 
import os.path

# Path
path = '/home/User/Documents/file.txt'

# Check whether the 
# specified path is an
# existing directory or not
isdir = os.path.isdir(path)
print(isdir)

# Path
path = '/home/User/Documents/'

# Check whether the 
# specified path is an
# existing directory or not
isdir = os.path.isdir(path)
print(isdir)
```

**输出:**

```py
False
True
```

**示例:**如果指定路径是符号链接。

## 蟒蛇 3

```py
# Python program to explain os.path.isdir() method 

# importing os.path module 
import os.path

# Create a directory
# (in current working directory)
dirname = "GeeksForGeeks"
os.mkdir(dirname)

# Create a symbolic link
# pointing to above directory
symlink_path = "/home/User/Desktop/gfg"
os.symlink(dirname, symlink_path)

path = dirname

# Now, Check whether the 
# specified path is an
# existing directory or not
isdir = os.path.isdir(path)
print(isdir)

path = symlink_path

# Check whether the 
# specified path (which is a
# symbolic link ) is an
# existing directory or not
isdir = os.path.isdir(path)
print(isdir)
```

**输出:**

```py
True
True
```

## 使用 pathlib。Path.exists()

**Python 中的 Pathlib 模块**提供了各种表示文件系统路径的类，其语义适合不同的操作系统。该模块属于 Python 的标准实用程序模块。**路径库模块**中的路径类分为**纯路径**和**具体路径**。纯路径仅提供计算操作，但不提供输入/输出操作，而从纯路径继承的具体路径提供计算和输入/输出操作。
**注:**要了解更多关于 pathlib 模块的信息[点击此处](https://www.geeksforgeeks.org/pathlib-module-in-python/)。
pathlib。Path.exists()方法用于检查给定路径是否指向现有文件或目录。

> **语法:** pathlib。Path.exists(path)
> **参数:**
> **路径:**表示文件系统路径的类路径对象。
> **返回类型:**该方法返回 bool 类的布尔值。如果路径存在，此方法返回真，否则返回假。

**例:**

## 蟒蛇 3

```py
# Import Path class
from pathlib import Path

# Path
path = '/home/gfg/Desktop'

# Instantiate the Path class
obj = Path(path)

# Check if path points to 
# an existing file or directory 
print(obj.exists())
```

**输出:**

```py
True
```