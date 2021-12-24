# Python 目录管理

> 原文:[https://www.geeksforgeeks.org/python-directory-management/](https://www.geeksforgeeks.org/python-directory-management/)

目录是在计算机上存储、组织和分离文件的一种方式。没有父目录的目录称为**根目录**。到达文件的路径称为**路径**。该路径包含目录名、由斜线和冒号分隔的文件夹名的组合，这给出了系统中文件的路径。

## 使用 Python 进行目录管理

Python 包含几个模块，这些模块有许多内置函数来操作和处理数据。Python 还提供了帮助我们与操作系统和文件交互的模块。这些类型的模块也可以用于目录管理。提供这些功能的模块如下所示:

*   os 和 os.path
*   filecmp
*   临时文件
*   舒蒂尔

### os 和 os.path 模块

os 模块用于以各种方式处理文件和目录。它提供创建/重命名/删除目录的规定。这甚至允许知道当前的工作目录并将其更改为另一个。它还允许用户将文件从一个目录复制到另一个目录。用于目录管理的主要方法解释如下。

#### 创建新目录:

*   **os.mkdir(name)** 方法创建新目录。
*   新目录所需的名称作为参数传递。
*   默认情况下，它会在当前工作目录中创建新目录。
*   如果必须在其他地方创建新目录，那么必须指定路径，并且路径应该包含正斜杠而不是反斜杠。

## 蟒蛇 3

```py
import os

# creates in current working directory
os.mkdir('new_dir') 

# creates in D:\
os.mkdir('D:/new_dir') 
```

#### 获取当前工作目录(CWD):

*   **可以使用 os.getcwd()** 。
*   它返回一个字符串，表示当前工作目录的路径。
*   **也可以使用 os.getcwdb()** 但是它会返回一个表示当前工作目录的字节字符串。
*   这两种方法都不需要传递任何参数。

## 蟒蛇 3

```py
import os

print("String format :", os.getcwd())
print("Byte string format :", os.getcwdb())
```

**输出:**

```py
String format : /home/nikhil/Desktop/gfg
Byte string format : b'/home/nikhil/Desktop/gfg'
```

#### 重命名目录:

*   **os.rename()** 方法用于重命名目录。
*   传递的参数是 old_name 后跟 new_name。
*   如果传递了 new_name 的目录已经存在，那么在 Unix 和 Windows 的情况下都会引发 OSError。
*   如果一个文件已经以 new_name 存在，在 Unix 中不会出现错误，该目录将被重命名。但是在 Windows 中，重命名不会发生，并且会引发错误。
*   **OS . rename(' old _ name '，' dest_dir:/new_name')** 方法的工作原理类似于 **os.rename()** ，但它将重命名的文件移动到指定的目标目录(dest_dir)。

例如，假设当前工作目录中有一个名为“file1.txt”的文件。现在给它重新命名:

## 蟒蛇 3

```py
import os

os.rename('file1.txt','file1_renamed.txt')
```

如果需要重命名文件并将文件移动到其他目录，那么代码片段应该是:

## 蟒蛇 3

```py
import os

os.renames('file1.txt', 'D:/file1_renamed.txt')
```

#### 更改当前工作目录(CWD):

*   计算机系统中的每个进程都有一个与之相关联的目录，称为当前工作目录(CWD)。
*   **os.chdir()** 方法用于更改。
*   传递的参数是希望移动到的所需目录的路径/名称。

例如，如果我们需要将 CWD 更改为 D:/中的 my_folder，则使用下面的代码片段。

## 蟒蛇 3

```py
import os

print("Current directory :", os.getcwd())

# Changing directory
os.chdir('/home/nikhil/Desktop/')
print("Current directory :", os.getcwd())
```

**输出:**

```py
Current directory : /home/nikhil/Desktop/gfg
Current directory : /home/nikhil/Desktop
```

#### 列出目录中的文件

*   一个目录可能包含子目录和许多文件。要列出它们，请使用 **os.listdir()** 方法。
*   它要么不带参数，要么带一个参数。
*   如果没有传递参数，则列出 CWD 的文件和子目录。
*   如果需要列出除 CWD 以外的任何其他目录的文件，则该目录的名称/路径作为参数传递。

例如:列出 CWD 极客目录中的文件

## 蟒蛇 3

```py
import os

print("The files in CWD are :",os.listdir(os.getcwd()))
```

**输出:**

> CWD 的文件是:['站点文件夹'，'。目录'，' proxy.txt '，'诗 python.txt '，'左栏'，'图片'，'欢迎来到 GeeksforGeeks！\ n 列表添加 Ne.txt '，'废纸篓. desktop '，' gfg.py '，'抱歉，您无法更新某些 tim.txt '，' gfgNikhil Aggarwal.png '，' 0001.jpg '，' gfg '，' gfgcerti.png '，' raju '，' images big']

#### 删除目录

*   **os.rmdir()** 方法用于删除/删除一个目录。
*   传递的参数是该目录的路径。
*   当且仅当目录为空时，它才会删除该目录，否则会引发 OSError。

例如，让我们考虑一个目录 K:/文件。现在要删除它，必须确保它是否为空，然后继续删除。

## 蟒蛇 3

```py
import os

dir_li=os.listdir('k:/files')

if len(dir_li)==0:
  print("Error!! Directory not empty!!")
else:
  os.rmdir('k:/files')
```

#### 要检查它是否是一个目录:

*   给定一个目录名或路径， **os.path.isdir(path)** 用于验证该路径是否为有效目录。
*   它只返回布尔值。如果给定路径是有效目录，则返回**真**，否则返回**假**。

## 蟒蛇 3

```py
import os

# current working directory of
# GeeksforGeeks
cwd='/'
print(os.path.isdir(cwd))

# Some other directory
other='K:/'
print(os.path.isdir(other))
```

**Output**

```py
True
False
```

#### 要获取目录的大小:

*   **OS . path . getsize(path _ name)**以字节为单位给出目录的大小。
*   如果将无效路径作为参数传递，则会引发 OSError。

## 蟒蛇 3

```py
import os

print(os.path.getsize(os.getcwd()))
```

**Output**

```py
4096
```