# Python–itertools . zip _ long()

> 原文:[https://www.geeksforgeeks.org/python-itertools-zip_longest/](https://www.geeksforgeeks.org/python-itertools-zip_longest/)

[Python 的 Itertool](https://www.geeksforgeeks.org/python-itertools/) 是一个提供各种函数的模块，这些函数在迭代器上工作，产生复杂的迭代器。这个模块作为一个快速、内存高效的工具，可以单独使用，也可以组合使用，形成迭代器代数。

Python 中的迭代器是一个可以像**序列数据类型**一样进行迭代的对象，比如**列表、元组、字符串**等等。

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## Itertools.zip _ longest()

这个迭代器属于[终止迭代器](https://www.geeksforgeeks.org/python-itertools/#terminate)的范畴。它按顺序交替打印数据项的值。如果其中一个表被完全打印，剩余的值由分配给`fillvalue`参数的值填充。

**语法:**

```
zip_longest( iterable1, iterable2, fillval)
```

**例 1:**

```
# Python code to demonstrate the working of   
# zip_longest()  

import itertools  

# using zip_longest() to combine two iterables.  
print ("The combined values of iterables is  : ")  
print (*(itertools.zip_longest('GesoGes', 'ekfrek', fillvalue ='_' )))  
```

**输出:**

```
The combined values of iterables is  : 
('G', 'e') ('e', 'k') ('s', 'f') ('o', 'r') ('G', 'e') ('e', 'k') ('s', '_')
```

**例 2:**

```
from itertools import zip_longest

x =[1, 2, 3, 4, 5, 6, 7]
y =[8, 9, 10]
z = list(zip_longest(x, y))
print(z)
```

**输出:**

```
[(1, 8), (2, 9), (3, 10), (4, None), (5, None), (6, None), (7, None)]
```