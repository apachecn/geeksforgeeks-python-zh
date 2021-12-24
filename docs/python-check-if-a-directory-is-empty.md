# Python:检查目录是否为空

> 原文:[https://www . geesforgeks . org/python-检查目录是否为空/](https://www.geeksforgeeks.org/python-check-if-a-directory-is-empty/)

Python 是一种广泛使用的通用高级编程语言。它提供了许多功能，其中之一是检查目录是否为空。这可以通过使用**操作系统模块**来实现。Python 中的 **[OS 模块](https://www.geeksforgeeks.org/os-module-python-examples/)** 提供了与操作系统交互的功能。`OS` 属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。`os` 和`os.path`模块包括许多与文件系统交互的功能。

#### 检查目录是否为空

检查目录是否为空`[os.listdir()](https://www.geeksforgeeks.org/python-os-listdir-method/)`方法被使用。`[os.listdir()](https://www.geeksforgeeks.org/python-os-listdir-method/)`OS 模块的方法是获取指定目录下所有文件和目录的列表。

> **语法:** os.listdir(路径)
> 
> **参数:**
> **路径(可选):**目录的路径
> 
> **返回类型:**该方法返回指定路径下所有文件和目录的列表。此方法的返回类型是 list。

**示例#1:** 如果`os.listdir()`返回的列表为空，则目录为空，否则不为空。下面是实现。

```
# Python program to check whether
# the directory empty or not

import os

# path of the directory
path = "D:/Pycharm projects/GeeksforGeeks/Nikhil"

# Getting the list of directories
dir = os.listdir(path)

# Checking if the list is empty or not
if len(dir) == 0:
    print("Empty directory")
else:
    print("Not empty directory")
```

**输出:**

```
Empty directory

```

**示例#2:** 假设上述代码中指定的路径是文本文件的路径或无效路径，那么，在这种情况下，上述代码将引发`OSError`。为了克服这个错误，我们可以使用`[os.path.isfile](https://www.geeksforgeeks.org/python-os-path-isfile-method/)()`方法和`[os.path.exists()](http://geeksforgeeks.org/python-os-path-exists-method/)`方法。下面是实现。

```
# Python program to check whether
# the directory is empty or not

import os

# Function to Check if the path specified
# specified is a valid directory
def isEmpty(path):
    if os.path.exists(path) and not os.path.isfile(path):

        # Checking if the directory is empty or not
        if not os.listdir(path):
            print("Empty directory")
        else:
            print("Not empty directory")
    else:
        print("The path is either for a file or not valid")

# path to a file
path = "D:/Pycharm projects/GeeksforGeeks/Nikhil/gfg.txt"
isEmpty(path)
print()

# valid path
path = "D:/Pycharm projects/GeeksforGeeks/Nikhil/"
isEmpty(path)
```

**输出:**

```
The path is either for a file or not valid

Not empty directory

```