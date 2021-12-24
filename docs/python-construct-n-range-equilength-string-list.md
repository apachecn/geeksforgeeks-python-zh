# Python |构造 N 范围等长字符串列表

> 原文:[https://www . geesforgeks . org/python-construct-n-range-equilength-string-list/](https://www.geeksforgeeks.org/python-construct-n-range-equilength-string-list/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们需要构建一个包含 N 个范围数字的字符串列表。但是我们有要求，我们需要保持每个元素的长度相等。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `zfill()`**
上述功能的组合可用于执行该任务。在本文中，我们使用列表理解来执行添加数字的任务，zfill()负责每个字符串所需的长度。

```py
# Python3 code to demonstrate working of
# Construct N Range Equilength String list
# using list comprehension + zfill()

# initialize N 
N = 6

# printing N 
print("Number of elements required : " + str(N))

# initialize K 
K = 3

# Construct N Range Equilength String list
# using list comprehension + zfill()
res = [str(ele).zfill(K) for ele in range(N)]

# printing result
print("K Length range strings list : " + str(res))
```

**Output :**

```py
Number of elements required : 6
K Length range strings list : ['000', '001', '002', '003', '004', '005']

```