# 如何在 Python 中从文件夹读取多个文本文件？

> 原文:[https://www . geesforgeks . org/如何从 python 文件夹中读取多个文本文件/](https://www.geeksforgeeks.org/how-to-read-multiple-text-files-from-folder-in-python/)

**先决条件:**

*   [文件处理](https://www.geeksforgeeks.org/file-handling-python/)
*   OS

Python 是一种很强的语言，即使在文件处理方面也非常强大。在本文中，我们将学习如何使用 python 从一个文件夹中读取多个文本文件。

**进场:**

*   导入模块
*   添加文件夹的路径
*   更改目录
*   从文件夹中获取文件列表
*   遍历文件列表，检查文件的扩展名是否在中。不管是否是 txt 格式。
*   如果存在文本文件，使用文件处理读取文件

**使用的功能:**

*   **Python 中的 os.chdir()** 方法，用于将当前工作目录更改为指定路径。它只接受一个参数作为新的目录路径。

> **语法:** os.chdir(path)
> 
> ***参数:***
> 
> *   ***路径:**要更改为新目录路径的目录的完整路径。*
> 
> ***返回:**不返回任何值*

*   ***os.listdir()*** 方法在 python 中用来获取指定目录下所有文件和目录的列表。如果我们没有指定任何目录，那么将返回当前工作目录中的文件和目录列表。

> ***语法:** os.listdir(路径)*
> 
> ***参数:***
> 
> *   *路径(可选) :目录的路径*
> 
> ***返回类型:**该方法返回指定路径下所有文件和目录的列表。此方法的返回类型是 list。*

以下是实施情况:

**程序:**

## 蟒蛇 3

```
# Import Module
import os

# Folder Path
path = "Enter Folder Path"

# Change the directory
os.chdir(path)

# Read text File

def read_text_file(file_path):
    with open(file_path, 'r') as f:
        print(f.read())

# iterate through all file
for file in os.listdir():
    # Check whether file is in text format or not
    if file.endswith(".txt"):
        file_path = f"{path}\{file}"

        # call read text file function
        read_text_file(file_path)
```

**输出:**

<video class="wp-video-shortcode" id="video-548054-1" width="640" height="360" preload="metadata" controls=""><source type="video/mp4" src="https://media.geeksforgeeks.org/wp-content/uploads/20210125102530/FreeOnlineScreenRecorderProject4.mp4?_=1">[https://media.geeksforgeeks.org/wp-content/uploads/20210125102530/FreeOnlineScreenRecorderProject4.mp4](https://media.geeksforgeeks.org/wp-content/uploads/20210125102530/FreeOnlineScreenRecorderProject4.mp4)</video>