# Python 的 print()函数的文件参数

> 原文:[https://www.geeksforgeeks.org/python-file-parameter-print/](https://www.geeksforgeeks.org/python-file-parameter-print/)

Python3 中的 **print()** 函数支持一个“*文件*参数，该参数指定函数应该将给定的对象写到哪里。如果没有明确说明，默认为 *sys.stdout* 。

它有两个基本目的:

```py
Print to STDERR
Print to external file
```

**注意:**只有在 Python 3.x 或更高版本中才能找到‘file’参数。

**打印至 STDERR :**

将文件参数指定为 sys.stderr，而不是默认值。这在调试小程序时非常有用(在其他情况下最好使用调试器)。

```py
# Code for printing to STDERR
import sys

print('GeeksForGeeks', file = sys.stderr)
```

**输出:**

```py
GeeksForGeeks

```

**打印到特定文件:**

用所需文件的名称指定文件参数，而不是默认值。如果文件不存在，将创建一个同名的新文件并写入其中。

```py
# Code for printing to a file
sample = open('samplefile.txt', 'w')

print('GeeksForGeeks', file = sample)
sample.close()
```

**输出*(在“samplefile.txt”中)* :**

```py
GeeksForGeeks

```

**注意:**在你的系统上的解释器中尝试这个，因为这样的文件不能在在线集成开发环境中访问。