# 使用 Python 找到给定文件的路径

> 原文:[https://www . geesforgeks . org/find-给定文件的路径-使用-python/](https://www.geeksforgeeks.org/find-path-to-the-given-file-using-python/)

我们可以获得运行脚本文件的位置(路径)。带 __file__ 的 py。 **__file__** 对于读取其他文件很有用，它给出了正在运行的文件的当前位置。版本不同。在 Python 3.8 和更低版本中，__file__ 返回执行 Python(或 Python 3)命令时指定的路径。如果指定了相对路径，我们就可以得到相对路径。如果我们指定一个绝对路径，就会返回一个绝对路径。但是在 Python 3.9 和更高版本中，__file__ 总是返回一个绝对路径，“os”模块提供了各种实用程序。

**os.getcwd():** 我们可以得到当前工作目录的绝对路径。因此，根据使用的版本，检索相对路径或绝对路径。

**例 1:**

## 蟒蛇 3

```py
import os
print('Get current working directory :      ', os.getcwd())
print('Get current file name :    ', __file__)
```

**输出:**

![](img/4c432d088406cba075bb77bf596b7b0c.png)

**例 2:** 我们可以通过下面的方式得到运行文件的文件名和目录名。

## 蟒蛇 3

```py
import os

print('File name :    ', os.path.basename(__file__))
print('Directory Name:     ', os.path.dirname(__file__))
```

**输出:**

![](img/e495e6e36f4307d64a57fb10f1d62846.png)

查找文件名和目录名的方法

**例 3:** 获取运行文件的绝对路径。

## 蟒蛇 3

```py
import os

print('Absolute path of file:     ', 
      os.path.abspath(__file__))
print('Absolute directoryname: ', 
      os.path.dirname(os.path.abspath(__file__)))
```

**输出:**

![](img/7f0da6be84ea28277d4b54e49fb166f0.png)

查找文件和目录名的绝对方法

**例 4:** 如果我们在 OS . path . abpath()中指定了一个绝对路径，那么它将按原样返回，所以如果 __file__ 是一个绝对路径，那么即使我们设置了 OS . path . abpath(_ _ file _ _)也不会出错

## 蟒蛇 3

```py
import os
pythonfile = 'pathfinding.py'

# if the file is present in current directory,
# then no need to specify the whole location
print("Path of the file..", os.path.abspath(pythonfile))

for root, dirs, files in os.walk(r'E:\geeksforgeeks\path_of_given_file'):
    for name in files:

          # As we need to get the provided python file, 
        # comparing here like this
        if name == pythonfile:  
            print(os.path.abspath(os.path.join(root, name)))
```

**输出:**

![](img/d1827d49dc24d6c48ea2d2e9457206f1.png)