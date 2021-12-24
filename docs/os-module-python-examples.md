# Python 中的操作系统模块，示例

> 原文:[https://www.geeksforgeeks.org/os-module-python-examples/](https://www.geeksforgeeks.org/os-module-python-examples/)

Python 中的操作系统模块提供了与操作系统交互的功能。操作系统属于 Python 的标准实用程序模块。该模块提供了一种使用操作系统相关功能的可移植方式。*os*和*os.path*模块包含许多与文件系统交互的功能。

## 处理当前工作目录

将**当前工作目录(CWD)** 视为一个文件夹，Python 正在其中运行。每当只通过名称调用文件时，Python 会假设它从 CWD 开始，这意味着只有当文件在 Python 的 CWD 中时，仅名称引用才会成功。
**注:**运行 Python 脚本的文件夹称为当前目录。这不是 Python 脚本所在的路径。
[**获取当前工作目录**](https://www.geeksforgeeks.org/get-directory-of-current-python-script/)
获取当前工作目录的位置使用 [os.getcwd()](https://www.geeksforgeeks.org/python-os-getcwd-method/) 。

**示例:**

## 蟒蛇 3

```
# Python program to explain os.getcwd() method

# importing os module
import os

# Get the current working
# directory (CWD)
cwd = os.getcwd()

# Print the current working
# directory (CWD)
print("Current working directory:", cwd)
```

**输出:**

```
Current working directory: /home/nikhil/Desktop/gfg
```

[**更改当前工作目录**](https://www.geeksforgeeks.org/change-current-working-directory-with-python/)

要更改当前工作目录(CWD) [os.chdir()](https://www.geeksforgeeks.org/python-os-chdir-method/) 方法被使用。此方法将 CWD 更改为指定路径。它只接受一个参数作为新的目录路径。

**注意:**当前工作目录是 Python 脚本运行的文件夹。

**示例:**

## 蟒蛇 3

```
# Python program to change the
# current working directory

import os

# Function to Get the current 
# working directory
def current_path():
    print("Current working directory before")
    print(os.getcwd())
    print()

# Driver's code
# Printing CWD before
current_path()

# Changing the CWD
os.chdir('../')

# Printing CWD after
current_path()
```

**输出:**

```
Current working directory before
C:\Users\Nikhil Aggarwal\Desktop\gfg

Current working directory after
C:\Users\Nikhil Aggarwal\Desktop
```

## 创建目录

操作系统模块中有不同的创建目录的方法。这些是–

*   os.mkdir()
*   os . makedirs()

### **使用 os.mkdir()**

Python 中的 os.mkdir()方法用于以指定的数值模式创建一个名为 path 的目录。如果要创建的目录已经存在，此方法将引发文件存在错误。

**示例:**

## 蟒蛇 3

```
# Python program to explain os.mkdir() method

# importing os module
import os

# Directory
directory = "GeeksforGeeks"

# Parent Directory path
parent_dir = "D:/Pycharm projects/"

# Path
path = os.path.join(parent_dir, directory)

# Create the directory
# 'GeeksForGeeks' in
# '/home / User / Documents'
os.mkdir(path)
print("Directory '% s' created" % directory)

# Directory
directory = "Geeks"

# Parent Directory path
parent_dir = "D:/Pycharm projects"

# mode
mode = 0o666

# Path
path = os.path.join(parent_dir, directory)

# Create the directory
# 'GeeksForGeeks' in
# '/home / User / Documents'
# with mode 0o666
os.mkdir(path, mode)
print("Directory '% s' created" % directory)
```

**输出:**

```
Directory 'GeeksforGeeks' created
Directory 'Geeks' created
```

### **使用 os.makedirs()**

Python 中的 os.makedirs()方法用于递归创建目录。这意味着在创建叶目录时，如果缺少任何中级目录，os.makedirs()方法将创建它们。

**示例:**

## 大蟒

```
# Python program to explain os.makedirs() method

# importing os module
import os

# Leaf directory
directory = "Nikhil"

# Parent Directories
parent_dir = "D:/Pycharm projects/GeeksForGeeks/Authors"

# Path
path = os.path.join(parent_dir, directory)

# Create the directory
# 'Nikhil'
os.makedirs(path)
print("Directory '% s' created" % directory)

# Directory 'GeeksForGeeks' and 'Authors' will
# be created too
# if it does not exists

# Leaf directory
directory = "c"

# Parent Directories
parent_dir = "D:/Pycharm projects/GeeksforGeeks/a/b"

# mode
mode = 0o666

path = os.path.join(parent_dir, directory)

# Create the directory 'c'

os.makedirs(path, mode)
print("Directory '% s' created" % directory)

# 'GeeksForGeeks', 'a', and 'b'
# will also be created if
# it does not exists

# If any of the intermediate level
# directory is missing
# os.makedirs() method will
# create them

# os.makedirs() method can be
# used to create a directory tree
```

**输出:**

```
Directory 'Nikhil' created
Directory 'c' created
```

## 用 Python 列出文件和目录

[**os.listdir()**](https://www.geeksforgeeks.org/python-os-listdir-method/) 方法在 Python 中用来获取指定目录下所有文件和目录的列表。如果我们没有指定任何目录，那么将返回当前工作目录中的文件和目录列表。

**示例:**

## 蟒蛇 3

```
# Python program to explain os.listdir() method

# importing os module
import os

# Get the list of all files and directories
# in the root directory
path = "/"
dir_list = os.listdir(path)

print("Files and directories in '", path, "' :")

# print the list
print(dir_list)
```

**输出:**

```
Files and directories in ' / ' :
['sys', 'run', 'tmp', 'boot', 'mnt', 'dev', 'proc', 'var', 'bin', 'lib64', 'usr', 
'lib', 'srv', 'home', 'etc', 'opt', 'sbin', 'media']
```

## 使用 Python 删除目录或文件

操作系统模块证明了 Python 中删除目录和文件的不同方法。这些是–

*   使用 os.remove()
*   使用 os.rmdir()

### **使用 os.remove()**

Python 中的 os.remove()方法用于移除或删除文件路径。此方法不能删除目录。如果指定的路径是目录，则该方法将引发 OSError。

**示例:**假设文件夹中包含的文件有:

![](img/ab3dc3d44c640b0606a6393b77842fc7.png)

## 蟒蛇 3

```
# Python program to explain os.remove() method

# importing os module
import os

# File name
file = 'file1.txt'

# File location
location = "D:/Pycharm projects/GeeksforGeeks/Authors/Nikhil/"

# Path
path = os.path.join(location, file)

# Remove the file
# 'file.txt'
os.remove(path)
e)
```