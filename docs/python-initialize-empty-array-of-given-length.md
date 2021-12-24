# Python–初始化给定长度的空数组

> 原文:[https://www . geeksforgeeks . org/python-initialize-empty-给定长度的数组/](https://www.geeksforgeeks.org/python-initialize-empty-array-of-given-length/)

**先决条件:**Python 中的[列表](https://www.geeksforgeeks.org/python-list/)

正如我们所知[数组](https://www.geeksforgeeks.org/python-arrays/)是存储在连续内存位置的项目集合。在 Python 中，[列表](https://www.geeksforgeeks.org/python-list/) ( [动态数组](https://www.geeksforgeeks.org/implementation-of-dynamic-array-in-python/))可以作为数组处理。在本文中，我们将学习如何初始化一个给定大小的空数组。

让我们看看不同的 Pythonic 方法来完成这项任务。

**方法 1–**

**语法:**

```py
list1 = [0] * size
list2 = [None] * size

```

```py
# initializes all the 10 spaces with 0’s
a = [0] * 10 

# initializes all the 10 spaces with None
b = [None] * 10 

# initializes all the 10 spaces with A's
c = ['A'] * 5 

# empty list which is not null, it's just empty.
d = [] 

print (a, "\n", b, "\n", c, "\n", d);
```

**Output:**

```py
[0, 0, 0, 0, 0, 0, 0, 0, 0, 0] 
[None, None, None, None, None, None, None, None, None, None] 
['A', 'A', 'A', 'A', 'A'] 
[]

```

**方法 2–**使用类似 C 的循环并指定大小。

**语法:**

```py
a = [0 for x in range(size)] #using loops

```

```py
a = []
b = []

# initialize the spaces with 0’s with 
# the help of list comprehensions
a = [0 for x in range(10)]
print(a)

# initialize multi-array 
b = [ [ None for y in range( 2 ) ]
             for x in range( 2 ) ]

print(b)
```

**Output:**

```py
[0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

[[None, None], [None, None]]

```

**方法 3–**使用 Numpy 创建空数组。

```py
import numpy

# create a simple array with numpy empty()
a = numpy.empty(5, dtype=object)
print(a)

# create multi-dim array by providing shape
matrix = numpy.empty(shape=(2,5),dtype='object')
print(matrix)
```

**输出:**

```py
[None None None None None]

[[None None None None None]
 [None None None None None]]

```