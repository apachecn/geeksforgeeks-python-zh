# __ Python 中的未来 _ _ 模块

> 原文:[https://www.geeksforgeeks.org/__future__-module-in-python/](https://www.geeksforgeeks.org/__future__-module-in-python/)

**__future__ module** 是 Python 中的内置模块，用于继承新 Python 版本中将提供的新功能..

该模块包括所有最新的函数，这些函数在 Python 的早期版本中没有出现。我们可以通过导入 __future__ 模块来使用它。它的版本是 Python 版本。__future__ 模块的基本思想是帮助迁移到使用 Python 3。十.特点。

**注意:**未来的语句必须在文件的顶部，否则 Python 解释器会引发语法错误

## 本模块中的以下功能:

<figure class="table">

| 特征 | 可选于 | 强制输入 |
| --- | --- | --- |
| 嵌套范围 | Two point one | Two point two |
| 发电机 | Two point two | Two point three |
| 分开 | Two point two | Three |
| 绝对导入 | Two point five | Three |
| with _ 语句 | Two point five | Two point six |
| 打印功能 | Two point six | Three |
| unicode 文字 | Two point six | Three |
| 发电机停止 | Three point five | Three point seven |
| 附注 | Three point seven | Three point one one |

</figure>

### 未来模块的基本功能:

Python 未来模块中有七个特性。

## 计算机编程语言

```py
import __future__
print(__future__.all_feature_names)
```

**输出:**

```py
['nested_scopes',  
'generators',
'division',
'absolute_import',
'with_statement',
'print_function',
'unicode_literals']
```

## __ 具有打印功能的未来 _ _ 模块

**例 1:**

Python2 打印语句不同于 Python3 打印功能。我们将 Python2 中的 Python 打印语句用作:

```py
print "Hello world"
```

但是我们可以在使用未来模块的 Python2 函数中使用 Python3 打印函数。

## 计算机编程语言

```py
# Code in Python 2
from __future__ import print_function

print("Hello world")
```

**输出:**

```py
Hello world
```

**例 2:**

这里我们将使用 Python 2 打印消息。Python 3 中带有结束属性的 x，“结束”在换行符中追加字符串。并且它会引发一个错误，因为该函数与 2.x 不兼容。

## 计算机编程语言

```py
# In 2.7 python compiler
print("Hello world", end=" ")
```

**输出:**

```py
File "main.py", line 1
    print("Hello world", end=" ")
                            ^
SyntaxError: invalid syntax
```

因此，通过 __future__ print 函数，我们可以在代码中导入这些功能，以使用最新的打印功能。

## 计算机编程语言

```py
# In 2.7 python compiler
from __future__ import print_function

print("Hello world", end=";")
```

**输出:**

```py
Hello world;
```

**例 3:**

sep 也属于 Python 3.x，但是这里我们将通过使用这个模块来使用这些属性。让我们在不使用未来模块的情况下检查这些属性。

## 蟒蛇 3

```py
# In 2.7 python compiler
print('Welcome ', ' Geeksforgeeks', sep = ' To ')
```

**输出:**

```py
  File "main.py", line 1
    print('Welcome ', ' Geeksforgeeks', sep=' To ')
                                           ^
SyntaxError: invalid syntax
```

然后让我们使用 __future__ print 函数来使用 sep 属性。

## 计算机编程语言

```py
# In 2.7 python compiler
from __future__ import print_function
print('Welcome ', ' Geeksforgeeks', sep=' To ')
```

**输出:**

```py
Welcome To Geeksforgeeks
```

## 具有除法功能的 __future__ 模块

这里我们将使用 Python2.x 和 Python3.x 中的除法函数

让我们看看 Python2.x 中的例子。

## 计算机编程语言

```py
# In 2.7 python compiler
print 7 / 5

print -7 / 5
```

**输出:**

```py
1.4
-1.4
```

让我们看看未来的模块，它会给你准确的结果。

## 计算机编程语言

```py
# In below python 2.x code, division works
# same as Python 3.x because we use  __future__

from __future__ import division

print 7 / 5
print -7 / 5
```

**输出:**

```py
1.4
-1.4
```

## __future__ 带有 [unicode 文字](https://www.geeksforgeeks.org/unicode_literals-in-python/)函数的模块

在 Python2.x 中，我们不能使用 Unicode，但是未来的模块允许我们使用 Unicode。

**例 1:**

在 Python2 中，字符串被视为字节字符串，但在更高版本中，所有字符串都被视为 Unicode 字符串。

## 计算机编程语言

```py
# code in Python2
print(type("Geeks"))
```

**输出:**

```py
<type 'str'>
```

让我们使用 Python2 中的未来模块。

## 计算机编程语言

```py
# code in Python2
from __future__ import unicode_literals

print(type("Geeks"))
```

**输出:**

```py
<type 'unicode'>
```

**例 2:**

让我们看看没有未来模块的例子，它会引发一个错误，因为我们正在构建一个保存 UTF 8 编码字节的字节字符串

## 计算机编程语言

```py
# encoding: utf-8
name = 'helló wörld from example'
print name.encode('utf8')
```

**输出:**

```py
Traceback (most recent call last):
  File "main.py", line 3, in <module>
    print name.encode('utf8')
UnicodeDecodeError: 'ascii' codec can't decode byte 0xc3 in position 4: ordinal not in range(128)
```

它可以在 Python2X 中用未来的模块来完成。

## 计算机编程语言

```py
# encoding: utf-8
from __future__ import unicode_literals
name = 'helló wörld from example'
print name.encode('utf8')
```

**输出:**

```py
helló wörld from example
```