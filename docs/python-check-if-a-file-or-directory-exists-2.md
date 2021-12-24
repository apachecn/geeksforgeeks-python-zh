# Python:检查文件或目录是否存在

> 原文:[https://www . geesforgeks . org/python-检查文件或目录是否存在-2/](https://www.geeksforgeeks.org/python-check-if-a-file-or-directory-exists-2/)

Python 是一种广泛使用的通用高级编程语言。它提供了许多功能，其中之一是检查文件或目录是否存在。这可以使用内置的**操作系统模块**来实现。

**[Python 中的 OS 模块](https://www.geeksforgeeks.org/os-module-python-examples/)** 提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。`os.path`模块是 Python 中 OS 模块的子模块，用于公共路径名操作。

## 检查文件是否存在

Python 中的`os.path.isfile()`方法用于检查指定的路径是否是现有的常规文件。

**注:** `os.path.isfile()`确实遵循符号链接。

> **语法:** os.path.isfile(路径)
> 
> **参数:**
> **路径:**表示文件系统路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> 
> **返回类型:**该方法返回 bool 类的布尔值。如果指定的路径是现有的常规文件，此方法返回 True，否则返回 False。

**Example:**

```
# Python program to explain os.path.isfile() method  

# importing os module  
import os 

# Path 
path = 'D:/Pycharm projects/GeeksforGeeks/Nikhil/test_nikhil.txt'

# Check whether the  
# specified path is  
# an existing file 
isFile = os.path.isfile(path) 
print(isFile)

# Path 
path = 'D:/Pycharm projects/GeeksforGeeks/Nikhil/'

# Check whether the  
# specified path is  
# an existing file 
isFile = os.path.isfile(path) 
print(isFile) 
```

**输出:**

```
True
False

```

#### 检查目录是否存在

Python 中的`os.path.isdir()`方法用于检查指定路径是否为现有目录。该方法遵循符号链接，这意味着如果指定的路径是指向目录的符号链接，那么该方法将返回`True`。

> **语法:** os.path.isdir(路径)
> 
> **参数:**
> **路径:**表示文件系统路径的类路径对象。
> 
> **返回类型:**该方法返回 bool 类的布尔值。如果指定的路径是现有目录，此方法返回 True，否则返回 False。

**示例#1:** 使用 os.path.isdir()方法。

```
# Python program to explain os.path.isdir() method  

# importing os.path module  
import os.path 

# Path 
path = 'D:/Pycharm projects/GeeksforGeeks/Nikhil/test_nikhil.txt'

# Check whether the  
# specified path is an 
# existing directory or not 
isdir = os.path.isdir(path) 
print(isdir) 

# Path 
path = 'D:/Pycharm projects/GeeksforGeeks/Nikhil/'

# Check whether the  
# specified path is an 
# existing directory or not 
isdir = os.path.isdir(path) 
print(isdir) 
```

**输出:**

```
False 
True

```

**示例#2:** 如果指定的路径是符号链接。

```
# Python program to explain os.path.isdir() method  

# importing os.path module  
import os.path 

# Create a directory 
# (in current working directory) 
dirname = "GeeksForGeeks"
os.mkdir(dirname) 

# Create a symbolic link 
# pointing to above directory 
symlink_path = "D:/Pycharm projects/GeeksforGeeks/Nikhil/"
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

```
True
True

```

#### 检查文件或目录是否存在

Python 中的`os.path.exists()`方法用于检查指定路径是否存在。这个方法也可以用来检查给定的路径是否引用了打开的文件描述符。只要您不在乎文件是否指向文件或目录，就可以使用它。

> **语法:** os.path.exists(路径)
> 
> **参数:**
> **路径:**表示文件系统路径的类路径对象。类似路径的对象是表示路径的字符串或字节对象。
> 
> **返回类型:**该方法返回 bool 类的布尔值。如果路径存在，此方法返回真，否则返回假。

**示例:**

```
# Python program to explain os.path.exists() method  

# importing os module  
import os 

# Path 
path = 'D:/Pycharm projects/GeeksforGeeks/Nikhil/test_nikhil.txt'

# Check whether the  
# specified path is  
# an existing file 
isExist = os.path.exists(path) 
print(isExist)

# Path 
path = 'D:/Pycharm projects/GeeksforGeeks/Nikhil/'

# Check whether the  
# specified path is  
# an existing file 
isExist = os.path.exists(path) 
print(isExist) 
```

**输出:**

```
True
True

```

**注意:** `os.path.exists()`函数可能会返回`False`，如果没有被授予对请求文件执行`os.stat()` 的权限，即使路径存在。