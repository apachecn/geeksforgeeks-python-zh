# 使用 Python 列出目录中某一类型的所有文件

> 原文:[https://www . geeksforgeeks . org/list-使用 python 在目录中列出特定类型的所有文件/](https://www.geeksforgeeks.org/list-all-files-of-certain-type-in-a-directory-using-python/)

在 python 中，有几个用于文件处理的内置模块和方法。这些功能存在于不同的模块中，如 os、glob 等。这篇文章帮助你在一个地方找到许多函数，它给你一个简单的知识，告诉你如何使用 python 编程在一个目录中列出某一类型的所有文件。

所以有三个特定的扩展，比如

*   使用操作系统。步行()
*   使用操作系统。listdir()
*   使用 glob。glob()

**使用的目录:**

![](img/4233dd70b2392eb5476f4fadbe169109.png)

路径名为 D:\GFG 的根文件夹的图像

***使用 os.walk()功能***

在 python 编程中，有不同的 os 模块，这些模块支持多种方法与文件系统交互。如上所述，它具有 walk()函数，通过自下而上或自上而下遍历目录，帮助我们列出特定路径中的所有文件，并返回三元组，如根、目录、文件

这里 root 是根目录或根文件夹，dir 是根目录的子目录，files 是根目录下的文件，它是一个子目录。

**语法:**

> os.walk(r'pathname ')

## 计算机编程语言

```py
import os
# traverse whole directory
for root, dirs, files in os.walk(r'D:\GFG'):
    # select file name
    for file in files:
        # check the extension of files
        if file.endswith('.png'):
            # print whole path of files
            print(os.path.join(root, file))
```

**输出:**

> D:\GFG\gfg_png_file.png

![](img/7b3e8b199e43385d23c34131b7f7a0fa.png)

os.walk()函数的输出

***使用操作系统。**功能*

Os 还有另一种方法可以帮助我们找到特定路径上的文件，称为 listdir()。它以随机顺序的列表格式返回在位置或路径中指定的目录中的所有文件名。它不包括“.”和“..”如果它们在输入文件夹中可用。

**语法:**

> os.listdir（'pathname'）

## 计算机编程语言

```py
import os
# return all files as a list
for file in os.listdir(r'D:\GFG'):
     # check the files which are end with specific extension
    if file.endswith(".png"):
        # print path name of selected files
        print(os.path.join(r'C:\GFG\Screenshots', file))
```

**输出:**

> D:\GFG\gfg_png_file.png

![](img/29bb1858e6910d5f3de435b06ccc73a9.png)

os.listdir()函数的输出

***使用 glob。glob()功能:***

在前面的例子中，我们必须遍历目录中名称与特定扩展名或模式匹配的文件列表。但是 glob modules 提供了查找具有特定扩展名或模式的文件列表的功能。这个函数有两个参数，一个是带有特定模式的路径名，它过滤掉所有文件，并将文件作为列表返回。另一个名为递归的参数在默认情况下是关闭的，这意味着 false。当其值为真时，该函数搜索其目录及其子目录。这里允许所有通配符，如“？”、“*”等。

**语法:**

> 路径名，递归=真

## 计算机编程语言

```py
import glob
import os
# glob.glob() return a list of file name with specified pathname
for file in glob.glob(r''D: \GFG' + "**/*.png", recursive=True):
  # print the path name of selected files
    print(os.path.join(r''D: \GFG', file))
```

**输出:**

> D:\GFG\gfg_png_file.png

![](img/29bb1858e6910d5f3de435b06ccc73a9.png)

glob.glob()函数的输出