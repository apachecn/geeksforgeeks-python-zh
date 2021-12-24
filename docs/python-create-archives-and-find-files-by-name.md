# Python |创建档案并按名称查找文件

> 原文:[https://www . geesforgeks . org/python-create-archives-and-find-files-by-name/](https://www.geeksforgeeks.org/python-create-archives-and-find-files-by-name/)

在本文中，我们将学习如何以常见格式(例如。焦油。tgz 或者。zip)使用 shutil 模块。

**shutil** 模块有两个功能——**`make_archive()`**和**`unpack_archive()`**——正好可以解决这个问题。

**代码#1 :**

```
import shutil
shutil.unpack_archive('Python-3.3.0.tgz')
shutil.make_archive('py33', 'zip', 'Python-3.3.0')
```

**输出:**

```
'/Users/Dell/Downloads/py33.zip'
```

`make_archive()`的第二个参数是所需的输出格式。要获取支持的归档格式列表，请使用`get_archive_formats()`。

**代码#2 :**

```
shutil.get_archive_formats()
```

**输出:**

```
[('bztar', "bzip2'ed tar-file"), 
 ('gztar', "gzip'ed tar-file"), 
 ('tar', 'uncompressed tar file'), 
 ('zip', 'ZIP file')]
```

Python 还有其他库模块，用于处理各种归档格式的低级细节(例如，tarfile、zipfile、gzip、bz2 等)。).然而，制作或提取一个档案，真的没有必要去这么低的水平。
可以只在 shutil 中使用这些高级功能来代替。这些函数有多种附加选项，用于日志记录、试运行、文件权限等。

让我们编写一个涉及查找文件的脚本，比如文件重命名脚本或日志归档器实用程序，但不必从 Python 脚本中调用 shell 实用程序，或者提供不容易通过“炮轰”获得的专门行为

要搜索文件，使用 **os.walk()** 函数，为其提供顶级目录。

**代码#3:查找特定文件名并打印出所有匹配项的完整路径的函数。**

```
import os

def findfile(start, name):
    for relpath, dirs, files in os.walk(start):

        if name in files:
            full_path = os.path.join(start, relpath, name)
            print(os.path.normpath(os.path.abspath(full_path)))

if __name__ == '__main__':
    findfile(sys.argv[1], sys.argv[2])
```

将此脚本保存为`abc.py`并从命令行运行它，将起点和名称作为位置参数输入如下–

```
bash % ./abc.py .myfile.txt
```

**它是如何工作的？**

*   `os.walk()`方法为我们遍历目录层次结构，对于它进入的每个目录，它返回一个三元组，包含它正在检查的目录的相对路径，包含该目录中所有目录名的列表，以及该目录中文件名的列表。
*   对于每个元组，只需检查目标文件名是否在文件列表中。如果是，`os.path.join()`用来组合一条路径。
*   为了避免出现类似`././foo//bar`的奇怪路径，使用了两个额外的函数来修复结果。
*   第一个是`os.path.abspath()`，走一条可能是相对的路，形成绝对的路。
*   第二个是`os.path.normpath()`，它将规范化路径，从而解决双斜线、对当前目录的多次引用等问题。

尽管与 UNIX 平台上的 find 实用程序相比，代码非常简单，但它具有跨平台的优势。此外，许多附加功能可以以可移植的方式添加，而无需做更多的工作。

**代码#4:打印出所有最近修改时间的文件的功能**

```
import os
import time

def modified_within(top, seconds):
    now = time.time()

    for path, dirs, files in os.walk(top):
        for name in files:
            fullpath = os.path.join(path, name)

            if os.path.exists(fullpath):
                mtime = os.path.getmtime(fullpath)
                if mtime > (now - seconds):
                    print(fullpath)

if __name__ == '__main__':
    import sys

    if len(sys.argv) != 3:
        print('Usage: {} dir seconds'.format(sys.argv[0]))
        raise SystemExit(1)

    modified_within(sys.argv[1], float(sys.argv[2]))
```

用不了多久，您就可以使用 os、os.path、glob 和类似模块的各种特性，在这个小函数的基础上构建复杂得多的操作。