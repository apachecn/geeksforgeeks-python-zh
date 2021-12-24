# python–etrtools . isice()

> 哎哎哎:# t0]https://www . geeksforgeeks . org/python-etrtools-isice/

在 Python 中， [Itertools](https://www.geeksforgeeks.org/python-itertools/) 是内置的模块，它允许我们以一种有效的方式处理迭代器。它们使得遍历像列表和字符串这样的数据项变得非常容易。其中一个 itertools 函数是 **islice()** 。

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## islice()函数

这个迭代器有选择地打印作为参数传递的可迭代容器中提到的值。

**语法:**

```py
islice(iterable, start, stop, step)

```

**例 1:**

```py
# Python program to demonstrate
# the working of islice

from itertools import islice

# Slicing the range function
for i in islice(range(20), 5): 
    print(i)

li = [2, 4, 5, 7, 8, 10, 20] 

# Slicing the list
print(list(itertools.islice(li, 1, 6, 2)))  
```

**输出:**

```py
0
1
2
3
4
[4, 7, 10]

```

**例 2:**

```py
from itertools import islice

for i in islice(range(20), 1, 5): 
    print(i)
```

**输出:**

```py
1
2
3
4

```

这里我们提供了三个参数`range()`，1 和 5。因此，第一个可作为范围的参数和第二个参数 1 将被视为起始值，5 将被视为终止值。

**例 3:**

```py
from itertools import islice

for i in islice(range(20), 1, 5, 2):
    print(i)
```

**输出:**

```py
1
3

```

这里我们提供四个参数`range()`作为可迭代的，1，5 和 2 作为停止值。因此，第一个可迭代为范围的参数和第二个参数 1 将被视为起始值，5 将被视为停止值，2 将被视为迭代值时跳过多少步的步长值。