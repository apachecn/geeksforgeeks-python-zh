# Python |计算元组中列表所有元素的出现次数

> 原文:[https://www . geesforgeks . org/python-计数-元组列表中所有元素的出现次数/](https://www.geeksforgeeks.org/python-count-occurrence-of-all-elements-of-list-in-a-tuple/)

给定一个元组和一个列表作为输入，编写一个 Python 程序来计算元组中列表所有项目的出现次数。

**示例:**

```
Input : tuple = ('a', 'a', 'c', 'b', 'd')
        list = ['a', 'b']
Output : 3 

Input : tuple = (1, 2, 3, 1, 4, 6, 7, 1, 4)
        list = [1, 4, 7]
Output : 6

```

**进场#1 :** 幼稚进场

第一种方法是幼稚的方法。使用 for 循环遍历给定的列表，并计算列表中每个元组的出现次数。最后，返回计数。

```
# Python3 Program to count occurrence 
# of all elements of list in a tuple
from collections import Counter

def countOccurrence(tup, lst):
    count = 0
    for item in tup:
        if item in lst:
            count+= 1

    return count 

# Driver Code
tup = ('a', 'a', 'c', 'b', 'd')
lst = ['a', 'b']
print(countOccurrence(tup, lst))
```

**Output:**

```
3

```

**方法 2 :** 从 Python Collections 模块中使用计数器
，导入计数器来解决给定的问题。计数器是一个容器，用于记录等值被添加的次数。将结果保存在“计数”中后，我们使用 for 循环，计算列表中的每个项目在“计数”中出现的次数，并对其求和以给出最终输出。

```
# Python3 Program to count occurrence 
# of all elements of list in a tuple
from collections import Counter

def countOccurrence(tup, lst):
    counts = Counter(tup)
    return sum(counts[i] for i in lst)

# Driver Code
tup = ('a', 'a', 'c', 'b', 'd')
lst = ['a', 'b']
print(countOccurrence(tup, lst))
```

**Output:**

```
3

```

**方法#3 :** 使用集合
解决给定问题的另一种方法是使用集合数据结构。只需将给定的列表转换成一个集合，这样就可以删除所有重复的列表。现在，对于列表中的每一项，计算它在元组中的出现次数，并将它们相加。

```
# Python3 Program to count occurrence 
# of all elements of list in a tuple

def countOccurrence(tup, lst):
    lst = set(lst)
    return sum(1 for x in tup if x in lst)

# Driver Code
tup = ('a', 'a', 'c', 'b', 'd')
lst = ['a', 'b']
print(countOccurrence(tup, lst))
```

**Output:**

```
3

```

**方法#4 :** 使用 Python 字典
在 Python 字典中获取元组的每一项及其出现频率作为关键字:值对，然后使用 for 循环，对于列表的每一项，统计其在元组中的出现次数并求和。

```
# Python3 Program to count occurrence 
# of all elements of list in a tuple

def countOccurrence(tup, lst):
    dct = {}
    for i in tup:
        if not dct.get(i):
            dct[i] = 0
        dct[i] += 1
    return sum(dct.get(i, 0) for i in lst)

# Driver Code
tup = ('a', 'a', 'c', 'b', 'd')
lst = ['a', 'b']
print(countOccurrence(tup, lst))
```

**Output:**

```
3

```

**进场# 5:**Python`numpy.in1d()`
Python numpy 给了我们一个直接找到给定问题解决方案的方法，那就是`numpy.in1d()`。这个方法测试一维数组的每个元素是否也存在于第二个数组中。由于 list 也是一维数组，所以这里可以应用这个方法。

```
# Python3 Program to count occurrence 
# of all elements of list in a tuple
import numpy as np

def countOccurrence(tup, lst):
    return np.in1d(tup, lst).sum()

# Driver Code
tup = ('a', 'a', 'c', 'b', 'd') 
lst = ['a', 'b']
print(countOccurrence(tup, lst))
```

**Output:**

```
3

```