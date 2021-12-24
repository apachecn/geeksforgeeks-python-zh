# Python–itertools . chain . from _ iterable()

> 原文:[https://www . geeksforgeeks . org/python-ITER tools-chain-from _ ITER able/](https://www.geeksforgeeks.org/python-itertools-chain-from_iterable/)

[Python 的 Itertool](https://www.geeksforgeeks.org/python-itertools/) 是一个提供各种函数的模块，这些函数在迭代器上工作，产生复杂的迭代器。这个模块作为一个快速、内存高效的工具，可以单独使用，也可以组合使用，形成迭代器代数。

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

itertools 下的功能可以分为三类

1.  产生[无限迭代器](https://www.geeksforgeeks.org/python-itertools/#infinite)的函数
2.  产生终止于最短输入序列的[迭代器的函数](https://www.geeksforgeeks.org/python-itertools/#terminate)
3.  产生[组合发电机](https://www.geeksforgeeks.org/python-itertools/#combine)的功能

## Chain.from_iterable()方法

函数`chain.from_iterable()`属于终止迭代器的范畴。该函数将单个可迭代表作为参数，并且输入可迭代表的所有元素也应该是可迭代的，并且它返回包含输入可迭代表的所有元素的扁平可迭代表。

```py
Syntax :
chain.from_iterable(iterable)

```

**示例#1:**

```py
# Importing chain class from itertools
from itertools import chain

# Single iterable containing iterable
# elements(strings) is passed as input
from_iterable = chain.from_iterable(['geeks',
                                     'for', 
                                     'geeks'])

# printing the flattened iterable
print(list(from_iterable))
```

**输出:**

> [‘g’、‘e’、‘e’、‘k’、‘s’、‘f’、‘o’、‘r’、‘g’、‘e’、‘e’、‘k’、‘s’]

**例 2:**

```py
# Importing chain class from itertools
from itertools import chain

# Single iterable containing iterable
# elements(strings and list) is passed
# as input
from_iterable = chain.from_iterable(['geeks', 
                                     'for',
                                     'geeks',
                                     ['w', 'i', 'n', 's']])

# printing the flattened iterable
print(list(from_iterable))
```

**输出:**

> ['g '，' e '，' e '，' k '，' s '，' f '，' o '，' r '，' g '，' e '，' e '，' k '，' s '，' w '，' I '，' n '，' s']