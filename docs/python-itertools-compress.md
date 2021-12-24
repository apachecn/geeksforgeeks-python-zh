# python–etrtools . compress()

> 原文:[https://www.geeksforgeeks.org/python-itertools-compress/](https://www.geeksforgeeks.org/python-itertools-compress/)

Python 的 [Itertool](https://www.geeksforgeeks.org/python-itertools/) 是一个提供各种函数的模块，这些函数在迭代器上工作以产生复杂的迭代器。这个模块作为一个快速、内存高效的工具，可以单独使用，也可以组合使用，形成迭代器代数。

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## 压缩()

`itertools.compress()`属于[终止迭代器](https://www.geeksforgeeks.org/python-itertools/#terminate)的范畴。这意味着这些迭代器用于处理短输入序列，并根据所用方法的功能产生输出。

**Compress():** 这个迭代器根据作为其他参数传递的布尔列表值，有选择地从传递的容器中挑选要打印的值。打印对应于布尔真的参数，否则跳过所有参数。

在本文中，我们给出了函数的两个参数。第一个参数是迭代器，第二个参数是选择器`True/1`或`False/0`。如果第一个参数对应的选择器是`True`，那么相应的数据就会被打印出来，我们就会得到相应的输出。

**语法:**

```
compress(iter, selector)
```

**例 1 :**

```
# Python code to demonstrate the working of   
# compress() 

import itertools
import operator

Codes =['C', 'C++', 'Java', 'Python']
selectors = [False, False, False, True]

Best_Programming = itertools.compress(Codes, selectors)

for each in Best_Programming:
    print(each)
```

**输出:**

```
Python

```

在上面的代码中，在代码列表中，我们存储了四个变量，在选择器列表中，我们有四个布尔值。当我们使用`itertools.compress()`时，值 False 被分配给“C”，False 被分配给“C++”，False 被分配给“Java”，True 被分配给“Python”。现在，在循环迭代的过程中，我们将得到赋值为真的输出。因此，在迭代“最佳编程”时，我们只得到“Python”。

**例 2 :**

```
# Python code to demonstrate the working of   
# compress() 

import itertools
import operator

example = itertools.compress('ABCDE', [1, 0, 1, 0, 0])

for each in example:
    print(each)
```

**输出:**

```
A
C

```