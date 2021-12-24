# Python–获取目录中按大小排序的文件列表

> 原文:[https://www . geesforgeks . org/python-获取目录中文件列表-按大小排序/](https://www.geeksforgeeks.org/python-get-list-of-files-in-directory-sorted-by-size/)

在本文中，我们将研究在 Python 编程语言中，以大小的排序顺序获取给定目录中文件列表的不同方法。

**获取目录中文件列表的两种不同方法按大小排序如下:**

*   使用 [os.listdir()](https://www.geeksforgeeks.org/python-os-listdir-method/) 功能
*   使用 [glob()](https://www.geeksforgeeks.org/how-to-use-glob-function-to-find-files-recursively-in-python/#:~:text=In%20Python%2C%20the%20glob%20module,to%20match%20pathnames%20in%20directories.) 功能

## **方法 1:** 使用 [os.listdir()](https://www.geeksforgeeks.org/python-os-listdir-method/) 功能

**使用 Python 中的 os.listdir()方法**获取指定目录下所有文件和目录的列表。如果我们没有指定任何目录，那么将返回当前工作目录中的文件和目录列表。

> **语法:** os.listdir(路径)
> 
> **参数:**路径(可选) :目录路径
> 
> **返回:**该方法返回指定路径下所有文件和目录的列表。此方法的返回类型是 list。

在这个方法中，我们将在一个文件夹中创建一个文件名列表，按照文件大小排序。我们将传递**λx:OS . stat(OS . path . join(dir _ name，x))。st_size** 作为 sorted()函数的关键参数，该函数将按大小对目录中的文件进行排序。

## 蟒蛇 3

```
import os

name_of_dir = 'dir_path'

# Storing list of all files
# in the given directory in list_of_files
list_of_files = filter( lambda x: os.path.isfile
                       (os.path.join(name_of_dir, x)),
                        os.listdir(dir_name) )

# Sort list of file names by size 
list_of_files = sorted( list_of_files,
                        key =  lambda x: os.stat
                       (os.path.join(name_of_dir, x)).st_size)

# Iterate over sorted list of file 
# names and print them along with size one by one 
for name_of_file in list_of_files:
    path_of_file = os.path.join(name_of_dir, name_of_file)
    size_of_file  = os.stat(path_of_file).st_size 
    print(size_of_file, ' -->', name_of_file)
```

**输出:**

```
366  --> descript.ion
1688  --> readme.txt
3990  --> License.txt
15360  --> Uninstall.exe
48844  --> History.txt
50688  --> 7-zip32.dll
78336  --> 7-zip.dll
108074  --> 7-zip.chm
186880  --> 7zCon.sfx
205824  --> 7z.sfx
468992  --> 7z.exe
581632  --> 7zG.exe
867840  --> 7zFM.exe
1679360  --> 7z.dll
```

## **方法二:U** 唱 [glob()](https://www.geeksforgeeks.org/how-to-use-glob-function-to-find-files-recursively-in-python/#:~:text=In%20Python%2C%20the%20glob%20module,to%20match%20pathnames%20in%20directories.) 功能

在 python 编程语言中，我们有 glob 模块，它提供了一个名为 glob()的函数，用于根据匹配模式在给定目录中查找文件或目录。使用 glob()函数，我们可以使用通配符和正则表达式来匹配和查找目录中的几个文件或目录中的所有文件。在这个方法中，我们将使用 glob()函数获得一个目录中所有文件的列表以及大小。步骤如下:

首先，我们将使用 glob()获得目录中所有文件的列表，然后使用 sorted()函数根据文件的大小对文件列表进行排序。

我们将使用 os.stat(file_path)。st_size 从文件的 stat 对象中获取文件大小。然后，我们将在 lambda 函数中传递封装的大小，作为 sorted()函数中的关键参数。

## 蟒蛇 3

```
import glob
import os

name_of_dir = 'dir_path/'

# Storing list of all files (file paths)
# in the given directory in list_of_files
list_of_files = filter( os.path.isfile,
                        glob.glob(name_of_dir + '*') )

# Sort list of files in directory by size 
list_of_files = sorted( list_of_files,
                        key =  lambda x: os.stat(x).st_size)

# Iterate over sorted list of file names
# and print them along with size one by one 
for path_of_file in list_of_files:
    size_of_file  = os.stat(path_of_file).st_size 
    print(size_of_file, ' -->', path_of_file)   
```

**输出:**

```
366  --> C:/Program Files/7-Zip\descript.ion
1688  --> C:/Program Files/7-Zip\readme.txt
3990  --> C:/Program Files/7-Zip\License.txt
15360  --> C:/Program Files/7-Zip\Uninstall.exe
48844  --> C:/Program Files/7-Zip\History.txt
50688  --> C:/Program Files/7-Zip\7-zip32.dll
78336  --> C:/Program Files/7-Zip\7-zip.dll
108074  --> C:/Program Files/7-Zip\7-zip.chm
186880  --> C:/Program Files/7-Zip\7zCon.sfx
205824  --> C:/Program Files/7-Zip\7z.sfx
468992  --> C:/Program Files/7-Zip\7z.exe
581632  --> C:/Program Files/7-Zip\7zG.exe
867840  --> C:/Program Files/7-Zip\7zFM.exe
1679360  --> C:/Program Files/7-Zip\7z.dll
```