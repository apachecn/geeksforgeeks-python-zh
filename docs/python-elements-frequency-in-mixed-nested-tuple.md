# Python–混合嵌套元组中的元素频率

> 原文:[https://www . geesforgeks . org/python-elements-frequency-in-mixed-nested-tuple/](https://www.geeksforgeeks.org/python-elements-frequency-in-mixed-nested-tuple/)

有时，在使用 Python 数据时，我们会遇到一个问题，即我们在单个元组中有嵌套和非嵌套形式的数据，我们希望计算它们中的元素频率。这种问题可能出现在网络开发和数据科学等领域。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = (5，(6，(7，8，6)))
> 输出 : {5: 1，6: 2，7: 1，8: 1}
> 
> **输入** : test_tuple = (5，6，7，8)
> **输出** : {5: 1，6: 1，7: 1，8: 1}

**方法#1:使用递归+循环**
这个问题的解决涉及两个步骤。首先，我们使用递归执行元组的展平，然后使用循环以强力方式执行计数。

```py
# Python3 code to demonstrate working of 
# Elements Frequency in Mixed Nested Tuple
# Using recursion + loop

# helper_fnc
def flatten(test_tuple):
    for tup in test_tuple:
        if isinstance(tup, tuple):
            yield from flatten(tup)
        else:
            yield tup

# initializing tuple
test_tuple = (5, 6, (5, 6), 7, (8, 9), 9)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Elements Frequency in Mixed Nested Tuple
# Using recursion + loop
res = {}
for ele in flatten(test_tuple):
    if ele not in res:
        res[ele] = 0
    res[ele] += 1

# printing result 
print("The elements frequency : " + str(res))
```

**Output :**

```py
The original tuple : (5, 6, (5, 6), 7, (8, 9), 9)
The elements frequency : {5: 2, 6: 2, 7: 1, 8: 1, 9: 2}

```

**方法 2:使用`Counter()` +回复**
这是解决这个问题的又一种方法。在本文中，我们使用 Counter()来执行对元素进行计数的任务。

```py
# Python3 code to demonstrate working of 
# Elements Frequency in Mixed Nested Tuple
# Using recursion + Counter()
from collections import Counter

# helper_fnc
def flatten(test_tuple):
    for tup in test_tuple:
        if isinstance(tup, tuple):
            yield from flatten(tup)
        else:
            yield tup

# initializing tuple
test_tuple = (5, 6, (5, 6), 7, (8, 9), 9)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Elements Frequency in Mixed Nested Tuple
# Using recursion + Counter()
res = dict(Counter(flatten(test_tuple)))

# printing result 
print("The elements frequency : " + str(res))
```

**Output :**

```py
The original tuple : (5, 6, (5, 6), 7, (8, 9), 9)
The elements frequency : {5: 2, 6: 2, 7: 1, 8: 1, 9: 2}

```