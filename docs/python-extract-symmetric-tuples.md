# Python–提取对称元组

> 原文:[https://www . geesforgeks . org/python-extract-对称-元组/](https://www.geeksforgeeks.org/python-extract-symmetric-tuples/)

有时在使用 Python 元组时，我们会遇到一个问题，即我们需要提取所有对称的对，即对于任何(x，y)，我们都有(y，x)对存在。这种问题可以应用于日常编程和 web 开发等领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(6，7)，(2，3)，(7，6)]
> **输出** : {(6，7)}
> 
> **输入** : test_list = [(6，7)，(2，3)]
> **输出** : {}

**方法#1:使用字典理解+ `set()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们首先构造反向对，然后与原始列表对进行比较，并提取其中的一个相等。set()用于删除重复项，以避免不必要的元素计算。

```
# Python3 code to demonstrate working of 
# Extract Symmetric Tuples
# Using dictionary comprehension + set()

# initializing list
test_list = [(6, 7), (2, 3), (7, 6), (9, 8), (10, 2), (8, 9)]

# printing original list
print("The original list is : " + str(test_list))

# Extract Symmetric Tuples
# Using dictionary comprehension + set()
temp = set(test_list) & {(b, a) for a, b in test_list}
res = {(a, b) for a, b in temp if a < b}

# printing result 
print("The Symmetric tuples : " + str(res)) 
```

**Output :**

```
The original list is : [(6, 7), (2, 3), (7, 6), (9, 8), (10, 2), (8, 9)]
The Symmetric tuples : {(8, 9), (6, 7)}

```

**方法 2:使用`Counter()` +列表理解**
这是执行这个任务的又一种方式。在这种情况下，我们遵循构建反向对的类似方法，但是在这里，我们计算相等的元素，计数为 2 的元素是重复的，并且匹配反向元组。

```
# Python3 code to demonstrate working of 
# Extract Symmetric Tuples
# Using Counter() + list comprehension
from collections import Counter

# initializing list
test_list = [(6, 7), (2, 3), (7, 6), (9, 8), (10, 2), (8, 9)]

# printing original list
print("The original list is : " + str(test_list))

# Extract Symmetric Tuples
# Using Counter() + list comprehension<
temp = [(sub[1], sub[0]) if sub[0] < sub[1] else sub for sub in test_list]
cnts = Counter(temp)
res = [key for key, val in cnts.items() if val == 2]

# printing result 
print("The Symmetric tuples : " + str(res)) 
```

**Output :**

```
The original list is : [(6, 7), (2, 3), (7, 6), (9, 8), (10, 2), (8, 9)]
The Symmetric tuples : [(7, 6), (9, 8)]

```