# Python–Itertools 组合()函数

> 原文:[https://www . geesforgeks . org/python-ITER tools-combinations-function/](https://www.geeksforgeeks.org/python-itertools-combinations-function/)

[Itertool](https://www.geeksforgeeks.org/python-itertools/) 是 Python 的一个模块，用于创建迭代器，帮助我们在空间和时间上高效循环。借助 itertools 的不同子功能，该模块帮助我们轻松解决复杂问题。不同的子功能分为 3 个子组，它们是

*   [无限迭代器](https://www.geeksforgeeks.org/python-itertools/#infinite)
*   [终止于最短输入序列的迭代器](https://www.geeksforgeeks.org/python-itertools/#terminate)
*   [组合发电机](https://www.geeksforgeeks.org/python-itertools/#combine)

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

## Itertools.combinations()

`Itertools.combinations()`属于名为“组合生成器”的第三个子类别。组合生成器是那些用于简化组合结构的迭代器，如排列、组合和笛卡尔乘积

按照名称组合的理解，是指迭代器中使用的一系列或一组数字或字母。类似地`itertools.combinations()`为我们提供了迭代器中使用的所有可能的元组、数字或字母的序列或集合，并且基于所有元素都不同的位置，假设元素是唯一的。所有这些组合都是按照字典顺序发出的。该函数将“r”作为输入，这里“r”代表可能的不同组合的大小。发出的所有组合的长度都是“r ”,这里“r”是一个必要的参数。

**语法:**

```py
combinations(iterator, r)
```

**实施例 1:-**

```py
# Combinations Of string "GeEKS" OF SIZE 3.

from itertools import combinations

letters ="GeEKS"

# size of combination is set to 3
a = combinations(letters, 3) 
y = [' '.join(i) for i in a]

print(y)
```

**输出:-**

```py
['G e E', 'G e K', 'G e S', 'G E K', 'G E S', 'G K S', 'e E K', 'e E S', 'e K S', 'E K S']

```

**实施例 2:-**

```py
from itertools import combinations

print ("All the combination of list in sorted order(without replacement) is:")   
print(list(combinations(['A', 2], 2)))  
print()  

print ("All the combination of string in sorted order(without replacement) is:")  
print(list(combinations('AB', 2)))  
print()  

print ("All the combination of list in sorted order(without replacement) is:")  
print(list(combinations(range(2), 1))) 
```

**输出:-**

```py
All the combination of list in sorted order(without replacement) is:
[('A', 2)]

All the combination of string in sorted order(without replacement) is:
[('A', 'B')]

All the combination of list in sorted order(without replacement) is:
[(0,), (1,)]

```