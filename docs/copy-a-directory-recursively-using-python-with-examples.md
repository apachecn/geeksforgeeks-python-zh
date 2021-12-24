# 使用 Python 递归复制目录(带示例)

> 原文:[https://www . geesforgeks . org/copy-a-directory-递归使用-python-with-examples/](https://www.geeksforgeeks.org/copy-a-directory-recursively-using-python-with-examples/)

**Python 中的 Shutil 模块**提供了很多对文件和文件集合进行高级操作的功能。它属于 Python 的标准实用程序模块。该模块有助于文件和目录复制和删除过程的自动化。
shutil.copytree()方法递归地将以源(src)为根的整个目录树复制到目标目录。由(dst) **命名的目标目录必须不存在**。它将在复制过程中创建。使用 [copystat()](https://www.geeksforgeeks.org/python-shutil-copystat-method/) 复制目录的权限和次数，使用 [shutil.copy2()](https://www.geeksforgeeks.org/python-shutil-copy2-method/) 复制单个文件。

> **语法:** shutil.copytree(src，dst，symlink = False，ignore = None，copy_function = copy2，ignore _ 悬空 _ symlink = False)
> **参数:**
> **src:** 代表源目录路径的字符串。
> **dest:** 代表目的地路径的字符串。
> **符号链接(可选):**此参数接受 True 或 False，具体取决于原始链接或链接链接的元数据将被复制到新的树中。
> **忽略(可选):**如果给定了忽略，它必须是一个可调用的，它将接收 copytree()访问的目录作为参数，以及 os.listdir()返回的目录列表。
> **copy_function(可选):**此参数默认值为 copy2。对于这个参数，我们可以使用像 copy()这样的其他复制函数。
> **忽略 _ 悬空 _ 符号链接(可选):**此参数值设置为真时，用于在符号链接所指向的文件不存在时对引发的异常进行静默。
> **返回值:**这个方法返回一个代表新创建目录路径的字符串。

**示例:**假设目录如下。

![python-shutil.copytree](img/b0d54b134cb4a4697a5a27b58bbe9006.png)

我们希望将文件夹“src”复制到新文件夹“dst”。下面是实现。

## 蟒蛇 3

```
# Python program to explain shutil.copytree() method 

# importing shutil module 
import shutil 

# path 
path = 'D:/Pycharm projects/GeeksforGeeks/' 

# Source path 
src = 'D:/Pycharm projects/GeeksforGeeks/src'

# Destination path 
dest = 'D:/Pycharm projects/GeeksforGeeks/dst'

# Copy the content of 
# source to destination 
destination = shutil.copytree(src, dest) 

# print(destination) prints the
# path of newly created file
```

**输出:**

![python-shutil.copytree](img/712909a03319395b7d9ae212194823a9.png)

#### 复制文件和目录

稍微调整一下上面的代码，我们就可以复制两个文件或目录。这可以使用 copytree()函数和 try-except 块来完成。我们将捕获异常，如果异常是 ENOTDIR，那么我们将使用 copy2()函数来复制文件。这样做允许我们使用单一代码复制文件和目录。

让我们假设目标目录如下所示。

![python-copy-files-and-directories](img/483c6faf8b239a7d8624d937b496634f.png)

我们希望将 src 文件夹中的文本文件复制到此目标文件夹。下面是实现。

## 蟒蛇 3

```
# Python program to demonstrate
# shutil.copytree()

# Importing module
import shutil
import errno

# Source path
src = 'D:/Pycharm projects/GeeksforGeeks/src/b/test_b.txt'

# Destination path
dest = 'D:/Pycharm projects/GeeksforGeeks/dst'

# Copy the content of
# source to destination
try:
    shutil.copytree(src, dest)
except OSError as err:

    # error caused if the source was not a directory
    if err.errno == errno.ENOTDIR:
        shutil.copy2(src, dest)
    else:
        print("Error: % s" % err)
```

**输出:**

![python-copy-files-and-directories](img/b7303e004001980ba439b94e6d2248c3.png)

#### 忽略文件和目录

有时，在将一个目录复制到另一个目录时，可能不想复制某些文件或子目录。甚至这也是由 shutil 模块处理的。copytree()函数接受 ignore 参数，该参数允许指定一个函数来返回应该忽略的目录或文件列表。该函数将文件或目录名作为参数，作为名称过滤器。如果传递的参数是在名称中，那么它将被添加到指定要跳过哪个文件或目录的 copytree()的列表中。

**示例:**假设源文件夹是这样的。

![python-copy-files-and-directories](img/95b4553dcb8386cbfb09ef077aba7503.png)

我们想用文件夹“a”复制上述文件夹的内容。下面是实现。

## 蟒蛇 3

```
# Python program to demonstrate
# shutil.copytree()

# importing modules
import shutil

# Declaring the ignore function
def ignoreFunc(file):
    def _ignore_(path, names):

        # List containing names of file
        # that are needed to ignore
        ignored = []

        # check if file in names
        # then add it to list
        if file in names:
            ignored.append(file)
        return set(ignored)

    return _ignore_

# Source path 
src = 'D:/Pycharm projects /GeeksforGeeks/src'

# Destination path 
dest = 'D:/Pycharm projects/GeeksforGeeks/dst'

# Copying the contents from Source
# to Destination without some
# specified files or directories
shutil.copytree(src, dest, ignore = ignoreFunc('a'))
```

**输出:**

![python-copy-files-and-directories](img/93afd5175a01f972e783a3e16db8b5de.png)

要删除多个文件或具有特定格式的文件，可以使用 shutil.ignore_patterns。该函数作为参数传递给 copytree()方法，该方法指定了用于过滤文件和目录的 glob 模式。

**示例:**我们将以上面的源文件夹为例，不会复制任何一个。txt 文件和文件夹“a”。下面是实现。

## 蟒蛇 3

```
# Python program to demonstrate
# shutil.copytree()

# importing modules
import shutil

# Source path 
src = 'D:/Pycharm projects/GeeksforGeeks/src'

# Destination path 
dest = 'D:/Pycharm projects/GeeksforGeeks/dst'

# Copying the contents from Source
# to Destination without some
# specified files or directories
shutil.copytree(src, dest, ignore = shutil.ignore_patterns('*.txt', 'a'))
```

**输出:**

![python-copy-files-and-directories](img/806aa6e1ad6e1a507699ad531f4d81e0.png)