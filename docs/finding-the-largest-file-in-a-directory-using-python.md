# 使用 Python 查找目录中最大的文件

> 原文:[https://www . geeksforgeeks . org/find-使用 python 在目录中查找最大的文件/](https://www.geeksforgeeks.org/finding-the-largest-file-in-a-directory-using-python/)

在本文中，我们将使用 Python 找到给定目录中最大的文件。我们将检查主目录及其每个子目录中的所有文件。

**所需模块:**
***os**:*
Python 中的 OS 模块提供了一种使用操作系统相关功能的方式。操作系统模块与 Python 的标准库一起提供，不需要安装。

**说明:**

*   文件夹路径被作为输入。然后我们使用 **[os.walk()](https://www.geeksforgeeks.org/os-walk-python/)** 函数遍历整个目录。
*   *os.walk()* 返回包含根文件夹名称、子目录列表和文件列表的元组。
*   **[os.stat()](https://www.geeksforgeeks.org/python-os-stat-method/)** 用于获取文件的状态， *st_size* 属性以字节为单位返回其大小。

下面是实现。

```
import os

# folder path input
print("Enter folder path")
path = os.path.abspath(input())

# for storing size of each 
# file
size = 0

# for storing the size of 
# the largest file
max_size = 0

# for storing the path to the 
# largest file
max_file =""

# walking through the entire folder,
# including subdirectories

for folder, subfolders, files in os.walk(path):

    # checking the size of each file
    for file in files:
        size = os.stat(os.path.join( folder, file  )).st_size

        # updating maximum size
        if size>max_size:
            max_size = size
            max_file = os.path.join( folder, file  )

print("The largest file is: "+max_file)
print('Size: '+str(max_size)+' bytes')
```

**输出:**

> **输入:**
> 输入文件夹路径
> /用户/标题/下载/wordpress
> 
> **输出:**
> 最大的文件是://Users/tithigosh/Downloads/WordPress/WP-includes/js/dist/components . js
> 大小:1792316 字节
> 
> **输入:**
> 输入文件夹路径
> /用户/标题/桌面
> 
> **输出:**
> 最大的文件是:/Users/tithigosh/Desktop/new/graph theory.pdf
> 大小:64061656 字节