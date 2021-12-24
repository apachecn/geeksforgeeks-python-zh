# Python |接受脚本输入

> 原文:[https://www . geesforgeks . org/python-accepting-script-input/](https://www.geeksforgeeks.org/python-accepting-script-input/)

很多人用 Python 代替 shell 脚本，用它来自动化常见的系统任务，比如操作文件、配置系统等等。本文旨在描述通过重定向、管道或输入文件接受脚本输入。

**问题–**让一个脚本能够使用任何对用户来说最简单的机制接受输入。这应该包括从命令到脚本的管道输出，将文件重定向到脚本，或者只是在命令行上将文件名或文件名列表传递给脚本。

Python 内置的 **fileinput** 模块使得这个非常简单简洁，如果脚本是这样的话。

**代码#1 :**

```py
import fileinput

with fileinput.input() as f_input:
    for line in f_input:
        print(line, end ='')
```

那么输入到脚本中已经可以通过前面提到的所有方式被接受。如果保存脚本并使其可执行，那么可以使用以下所有代码获得预期的输出:

**代码# 2:**

```py
# Prints a directory listing to stdout.
$ ls | ./filein.py 

# Reads/etc/passwd to stdout.
$ ./filein.py/etc/passwd 

# Reads/etc/passwd to stdout.
$ ./filein.py < /etc/passwd 
```

**file input . input()**函数创建并返回一个 **FileInput** 类的实例。除了包含一些方便的助手方法，实例还可以用作上下文管理器。因此，将所有这些放在一起，如果一个人写了一个脚本，期望同时打印几个文件的输出，他可能会让它在输出中包含文件名和行号，如下面给出的代码所示–

**代码#3 :**

```py
import fileinput
with fileinput.input('/etc/passwd') as f:
    for line in f:
        print(f.filename(), f.lineno(), line, end ='')
```

```py
/etc/passwd1
/etc/passwd2
/etc/passwd3 

<other output omitted>
```

使用它作为上下文管理器可以确保文件在不再使用时被关闭，并且可以在这里利用一些方便的文件输入助手方法来获取输出中的一些额外信息。