# 如何在 Python 中移动文件和目录

> 原文:[https://www . geesforgeks . org/如何在 python 中移动文件和目录/](https://www.geeksforgeeks.org/how-to-move-files-and-directories-in-python/)

Python 提供了将文件或目录从一个位置移动到另一个位置的功能。这可以通过使用 **shutil** 模块中的`[shutil.move()](https://www.geeksforgeeks.org/python-shutil-move-method/)`功能来实现。`shutil.move()`方法递归地将文件或目录(源)移动到另一个位置(目标)并返回目标。如果目标目录已经存在，那么 src 将被移动到该目录中。如果目的地已经存在，但不是一个目录，那么它可能会被覆盖，这取决于`os.rename()`语义。

> **语法:** shutil.move(源，目标，copy_function = copy2)
> 
> **参数:**
> **来源:**代表源文件路径的字符串。
> **目的地:**表示目的地目录路径的字符串。
> **copy_function(可选):**此参数默认值为 copy2。对于这个参数，我们可以使用其他复制函数，如 copy、copytree 等。
> 
> **返回值:**这个方法返回一个字符串，代表新创建的文件的路径。

**Example #1:** Suppose the structure of directory looks like this –

![Python-list-of-directories](img/4f9f42af6ffc45aec58433ca8cfd7765.png)

**内部测试:**

![python-move-files-and-dir](img/124b6d462cf410f2e2c38aedae6c4e31.png)

**内甲:**

![python-move-files-and-dir](img/dad29e6f1b7f07aac8fb0918ff48ec56.png)

我们想把目录 B 移到目录 a，下面是实现。

```
# Python program to move
# files and directories

import shutil

# Source path
source = "D:\Pycharm projects\gfg\Test\B"

# Destination path
destination = "D:\Pycharm projects\gfg\Test\A"

# Move the content of
# source to destination
dest = shutil.move(source, destination)

# print(dest) prints the 
# Destination of moved directory
```

**输出:**

**内部测试:**

![python-move-files-and-dir](img/b22122e5ed13013c0e395bcc65b242e1.png)

**内甲:**

![python-move-files-and-dir](img/829961d9073e76835821fb517519b3e1.png)

**示例#2:** 现在假设我们要使用`shutil.copytree()`将上述目录 A 的所有子目录和文件移动到目录 G，并且目标目录不存在。下面是实现。

```
# Python program to move
# files and directories

import shutil

# Source path
source = "D:\Pycharm projects\gfg\Test\A"

# Destination path
destination = "D:\Pycharm projects\gfg\Test\G"

# Move the content of
# source to destination
dest = shutil.move(source, destination, copy_function = shutil.copytree)

# print(dest) prints the
# Destination of moved directory
```

**输出:**

**内部测试:**

![python-move-files-and-dir](img/198a67b2eea0e023ab4085252093ccf7.png)

**内 G:**

![python-move-files-and-dir](img/1384a272d87e68ec6475cdf812a531e1.png)