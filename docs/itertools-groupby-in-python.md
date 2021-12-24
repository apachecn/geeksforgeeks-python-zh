# tettools . group by()在 Python

中

> 原文:[https://www.geeksforgeeks.org/itertools-groupby-in-python/](https://www.geeksforgeeks.org/itertools-groupby-in-python/)

**先决条件:** [Python Itertools](https://www.geeksforgeeks.org/python-itertools/)

Python 的 Itertool 是一个模块，它提供了各种在迭代器上工作的函数来产生复杂的迭代器。这个模块作为一个快速、内存高效的工具，可以单独使用，也可以组合使用，形成迭代器代数。

#### itertools.groupby()的缩写形式

此方法计算 iterable 中每个元素的键。它返回分组项的关键字和可重复项。

> **语法:** itertools.groupby(可迭代，key_func)
> 
> **参数:**
> **可迭代:**可迭代可以是任何类型(列表、元组、字典)。
> **键:**为可迭代表中的每个元素计算键的函数。
> 
> **返回类型:**它从可迭代中返回连续的键和组。如果键函数未指定或为“无”，则键默认为标识函数，并返回元素不变。

**例 1:**

```
# Python code to demonstrate 
# itertools.groupby() method 

import itertools

L = [("a", 1), ("a", 2), ("b", 3), ("b", 4)]

# Key function
key_func = lambda x: x[0]

for key, group in itertools.groupby(L, key_func):
    print(key + " :", list(group))
```

**输出:**

```
a : [('a', 1), ('a', 2)]
b : [('b', 3), ('b', 4)]

```

**例 2 :**

```
# Python code to demonstrate 
# itertools.groupby() method 

import itertools

a_list = [("Animal", "cat"), 
          ("Animal", "dog"), 
          ("Bird", "peacock"), 
          ("Bird", "pigeon")]

an_iterator = itertools.groupby(a_list, lambda x : x[0])

for key, group in an_iterator:
    key_and_group = {key : list(group)}
    print(key_and_group)
```

**输出**

```
{'Animal': [('Animal', 'cat'), ('Animal', 'dog')]}
{'Bird': [('Bird', 'peacock'), ('Bird', 'pigeon')]}

```