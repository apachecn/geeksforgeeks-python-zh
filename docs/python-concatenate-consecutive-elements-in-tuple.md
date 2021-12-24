# Python–连接元组中的连续元素

> 原文:[https://www . geesforgeks . org/python-concatenate-continuous-in-elements-tuple/](https://www.geeksforgeeks.org/python-concatenate-consecutive-elements-in-tuple/)

有时，在处理数据时，我们可能会遇到需要寻找累积结果的问题。这可以是任何类型、乘积或总和。这里我们将讨论相邻元素的连接。让我们讨论执行这项任务的某些方法。

**方法#1:使用`zip() + generator expression + tuple()`**
上述功能的组合可用于执行该任务。在本文中，我们使用生成器表达式来提供串联逻辑，同时的元素配对由 zip()完成。使用元组()将结果转换为元组形式。

```
# Python3 code to demonstrate working of
# Consecutive element concatenation in Tuple
# using zip() + generator expression + tuple

# initialize tuple
test_tup = ("GFG ", "IS ", "BEST ", "FOR ", "ALL ", "GEEKS")

# printing original tuple
print("The original tuple : " + str(test_tup))

# Consecutive element concatenation in Tuple
# using zip() + generator expression + tuple
res = tuple(i + j for i, j in zip(test_tup, test_tup[1:]))

# printing result
print("Resultant tuple after consecutive concatenation : " + str(res))
```

**Output :**

```
The original tuple : ('GFG ', 'IS ', 'BEST ', 'FOR ', 'ALL ', 'GEEKS')
Resultant tuple after consecutive concatenation : ('GFG IS ', 'IS BEST ', 'BEST FOR ', 'FOR ALL ', 'ALL GEEKS')

```