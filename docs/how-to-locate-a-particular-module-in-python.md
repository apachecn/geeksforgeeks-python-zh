# 如何在 Python 中定位特定模块？

> 原文:[https://www . geesforgeks . org/如何找到特定的 python 模块/](https://www.geeksforgeeks.org/how-to-locate-a-particular-module-in-python/)

在本文中，我们将看到如何在 Python 中定位特定的模块？定位模块意味着找到导入模块的目录。当我们导入一个模块时，Python 解释器以下列方式搜索该模块:

*   首先，它在当前目录中搜索模块。
*   如果在当前目录中没有找到该模块，Python 会在 shell 变量[和 PYTHONPATH](https://www.geeksforgeeks.org/pythonpath-environment-variable-in-python/) 中搜索每个目录。 [PYTHONPATH](https://www.geeksforgeeks.org/pythonpath-environment-variable-in-python/) 是一个环境变量，由目录列表组成。
*   如果同样失败，python 会检查安装 Python 时配置的安装相关目录列表。

[系统路径](https://www.geeksforgeeks.org/sys-path-in-python/)包含当前目录列表、PYTHONPATH 和安装相关默认值。在本文中，我们将讨论如何使用这个方法和其他方法来定位模块。

### **方法 1:使用 os 模块**

对于一个纯 python 模块，我们可以通过 module_name 找到它的来源。__ 文件 _ _。这将返回模块所在的位置。py 文件存在。要获取目录，我们可以使用 [os](https://www.geeksforgeeks.org/os-module-python-examples/) 模块中的 [os.path.dirname()](https://www.geeksforgeeks.org/python-os-path-dirname-method/) 方法。例如，如果我们想使用这种方法知道“随机”模块的位置，我们将在 python 文件中键入以下内容

## 计算机编程语言

```py
# importing random module
import random

# importing the os module
import os

# storing the path of modules file 
# in variable file_path
file_path = random.__file__

# storing the directory in dir variable
dir = os.path.dirname(file_path)

# printing the directory
print(dir)
```

**输出:**

```py
C;\Users\Lenovo\AppData\Local\Programs\Python\Python39\lib
```

### **方法 2:使用系统路径**

对于这种方法，我们将使用[系统](https://www.geeksforgeeks.org/python-sys-module/)模块。 [sys](https://www.geeksforgeeks.org/python-sys-module/) 模块的 [sys.path](https://www.geeksforgeeks.org/sys-path-in-python/) 变量包含所有在运行时搜索模块的目录。因此，通过了解这些目录，我们可以手动检查特定模块的位置。为了实现这一点，我们必须用 python shell 编写以下内容:-

## 计算机编程语言

```py
# importing sys module
import sys

# importing sys.path
print(sys.path)
```

这将返回运行时将为模块搜索的所有目录的列表。

**输出:**

> ['/home '，'/usr/lib/python2.7 '，'/usr/lib/python 2.7/plat-x86 _ 64-Linux-GNU '，'/usr/lib/python2.7/lib-tk '，
> 
> /usr/lib/python2.7/lib-old '，'/usr/lib/python2.7/lib-dynload '，'/usr/local/lib/python 2.7/dist-packages '，
> 
> /usr/lib/python 2.7/dist-packages ']

### **方法 3:使用帮助(模块名)**

在 python shell 中，在我们导入一些模块之后，我们可以使用 help(module_name)获得关于该模块的各种信息。例如，如果我们想知道使用这种方法的模块操作系统的位置，我们将在 python shell 中键入以下内容

## 计算机编程语言

```py
# importing os module
import os

# printing help(os)
print(help(os))
```

在各种信息下，我们会找到一个名为“文件”的标题，在该标题下会显示模块的位置。

**输出:**

> ….
> 
> /各种其他信息/
> 
> ….
> 
> 文件
> 
> c:\ user \ Lenovo \ app data \ local \ programs \ python \ python 39 \ lib \ OS . py

### **方法 4:使用检查模块**

我们也可以使用 python 中的[检查](https://www.geeksforgeeks.org/inspect-module-in-python/)模块来定位一个模块。我们将使用 inspect 模块的 inspect.getfile()方法来获取路径。此方法将把模块的名称作为参数，并将返回其路径。例如，如果我们想使用此方法找到 os 模块的目录，我们将编写以下代码:

## 计算机编程语言

```py
# importing random module
import inspect

# importing the os module
import os

# printing the file path of os module
print(inspect.getfile(os))
```

**输出:**

> c:\ user \ Lenovo \ AppData \ Local \ Programs \ Python \ Python 39 \ lib \ OS . py