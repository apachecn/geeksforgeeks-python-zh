# Python |通过将每个元素填充 N 来增加列表大小

> 原文:[https://www . geeksforgeeks . org/python-按填充增加列表大小-按 n 增加每个元素/](https://www.geeksforgeeks.org/python-increase-list-size-by-padding-each-element-by-n/)

给定一个列表和一个整数 N，编写一个 Python 程序，通过将每个元素填充 N 来增加列表的大小

**示例:**

```
Input : lst = [1, 2, 3]
        N = 3
Output : [1, 1, 1, 2, 2, 2, 3, 3, 3]

Input : lst = ['cats', 'dogs']
        N = 2
Output : ['cats', 'cats', 'dogs', 'dogs']

```

**方法#1 :** 列表理解

```
# Python3 program to increase list size 
# by padding each element by N

def increaseSize(lst, N):

    return [el for el in lst for _ in range(N)]

# Driver code
lst = [1, 2, 3]
N = 3
print(increaseSize(lst, N))
```

**Output:**

```
[1, 1, 1, 2, 2, 2, 3, 3, 3]

```

**使用`functools.reduce()`方法接近#2 :**

*reduce* 函数将参数中传递的特定函数应用于所有列表元素。因此，在这种方法中，我们在每个元素上应用一个函数，它的出现乘以 n

```
# Python3 program to increase list size 
# by padding each element by N
from functools import reduce

def increaseSize(lst, N):

    return reduce(lambda x, y: x + y, [[el]*N for el in lst])

# Driver code
lst = [1, 2, 3]
N = 3
print(increaseSize(lst, N))
```

**Output:**

```
[1, 1, 1, 2, 2, 2, 3, 3, 3]

```

**方法 3 :** 使用 *itertools.chain()*

```
# Python3 program to increase list size 
# by padding each element by N
from itertools import chain

def increaseSize(lst, N):

    return list(chain(*([el]*N for el in lst)))

# Driver code
lst = [1, 2, 3]
N = 3
print(increaseSize(lst, N))
```

**Output:**

```
[1, 1, 1, 2, 2, 2, 3, 3, 3]

```