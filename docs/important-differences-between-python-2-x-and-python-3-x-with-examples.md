# Python 2 . x 和 Python 3.x 的重要区别，附示例

> 原文:[https://www . geeksforgeeks . org/重要-python-2-x 和 python-3-x 之间的区别-带示例/](https://www.geeksforgeeks.org/important-differences-between-python-2-x-and-python-3-x-with-examples/)

*   [分部操作员](#Division operator)
*   [打印功能](#print function)
*   [Unicode](#Unicode)
*   外部参照
*   [错误处理](#Error Handling)
*   [_ 未来 _ 模块](#__future__ module)

**分部操作员**

如果我们在 python 2.x 中移植我们的代码或执行 python 3.x 代码，如果整数除法的更改没有被注意到(因为它不会引发任何错误)，这将是危险的。在移植我们的代码时，最好使用浮点值(如 7.0/5 或 7/5.0)来获得预期的结果。

## 计算机编程语言

```py
print 7 / 5

print -7 / 5    

'''

Output in Python 2.x

1

-2

Output in Python 3.x :

1.4

-1.4

# Refer below link for details

# https://www.geeksforgeeks.org/division-operator-in-python/

'''
```

**打印功能**

这是最广为人知的变化。在这种情况下，Python 2.x 中的 **print** 关键字被 Python 3.x 中的 **print()** 函数替换。但是，如果在 **print** 关键字后添加空格，括号在 Python 2 中起作用，因为解释器将其评估为表达式。

## 计算机编程语言

```py
print 'Hello, Geeks'      # Python 3.x doesn't support

print('Hope You like these facts')

'''

Output in Python 2.x :

Hello, Geeks

Hope You like these facts

Output in Python 3.x :

File "a.py", line 1

    print 'Hello, Geeks'

                       ^

SyntaxError: invalid syntax

Refer below link for details

https://www.geeksforgeeks.org/g-fact-25-print-single-multiple-variable-python/

'''
```

正如我们所看到的，如果我们在 python 2.x 中使用括号，那么就没有问题，但是如果我们在 python 3.x 中不使用括号，我们就会得到语法错误。

**Unicode:**

在 Python 2 中，隐式字符串类型是 ASCII。但是在 Python 3.x 中，隐式字符串类型是 Unicode。

## 计算机编程语言

```py
print(type('default string '))

print(type(b'string with b '))

'''

Output in Python 2.x (Bytes is same as str)

<type 'str'>

<type 'str'>

Output in Python 3.x (Bytes and str are different)

<class 'str'>

<class 'bytes'>

'''
```

Python 2.x 也支持 Unicode

## 计算机编程语言

```py
print(type('default string '))

print(type(u'string with b '))

'''

Output in Python 2.x (Unicode and str are different)

<type 'str'>

<type 'unicode'>

Output in Python 3.x (Unicode and str are same)

<class 'str'>

<class 'str'>

'''
```

外部参照:

Python 2.x 的 xrange()在 Python 3.x 中不存在，在 Python 2.x 中，range 返回列表即 range(3)返回[0，1，2]，而 xrange 返回 xrange 对象即 xrange(3)返回迭代器对象，其工作方式类似于 Java 迭代器，需要时会生成 number。
如果我们需要多次迭代同一个序列，我们更喜欢 range()，因为 range 提供了一个静态列表。xrange()每次都会重构序列。xrange()不支持切片和其他列表方法。xrange()的优点是，当任务是在大范围内迭代时，它可以节省内存。
在 Python 3.x 中，range 函数现在执行的是 xrange 在 Python 2.x 中执行的操作，因此为了保持代码的可移植性，我们可能希望坚持使用 range 来代替。所以 Python 3.x 的范围函数*就是 Python 2.x 的*xrange

## 计算机编程语言

```py
for x in xrange(1, 5):

    print(x),

for x in range(1, 5):

    print(x),

'''

Output in Python 2.x

1 2 3 4 1 2 3 4

Output in Python 3.x

NameError: name 'xrange' is not defined

'''
```

**错误处理:**

两个版本的错误处理都有一个小的变化。在 python 3.x 中，“as”关键字是必需的。

## 计算机编程语言

```py
try:

    trying_to_check_error

except NameError, err:

    print err, 'Error Caused'   # Would not work in Python 3.x

'''

Output in Python 2.x:

name 'trying_to_check_error' is not defined Error Caused

Output in Python 3.x :

File "a.py", line 3

    except NameError, err:

                    ^

SyntaxError: invalid syntax

'''
```

## 计算机编程语言

```py
try:

     trying_to_check_error

except NameError as err: # 'as' is needed in Python 3.x

     print (err, 'Error Caused')

'''

Output in Python 2.x:

(NameError("name 'trying_to_check_error' is not defined",), 'Error Caused')

Output in Python 3.x :

name 'trying_to_check_error' is not defined Error Caused

'''
```

**__ 未来 _ _ 模块:**

这基本上不是两个版本的区别，而是这里要提的一个有用的东西。__future__ 模块的想法是帮助迁移到 Python 3.x.
如果我们计划在 2.x 代码中支持 Python 3.x，我们可以在代码中使用 **_future_** 导入。
例如，在下面的 Python 2.x 代码中，我们使用了 Python 3.x 的整数除法行为，使用了 __future__ 模块。

## 计算机编程语言

```py
# In below python 2.x code, division works

# same as Python 3.x because we use  __future__

from __future__ import division

print 7 / 5

print -7 / 5
```

输出:

```py
1.4 

-1.4 
```

我们在 Python 2.x 中使用 __future__ 模块使用括号的另一个例子:

## 计算机编程语言

```py
from __future__ import print_function    

print('GeeksforGeeks')
```

输出:

```py
GeeksforGeeks 
```

关于 __future__ 模块的更多详细信息，请参考本中的[。](https://docs.python.org/2/library/__future__.html) 

本文由 **Arpit Agarwal** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。