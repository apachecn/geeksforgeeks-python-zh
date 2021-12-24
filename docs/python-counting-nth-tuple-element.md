# Python |计数第 n 个元组元素

> 原文:[https://www . geesforgeks . org/python-counting-n th-tuple-element/](https://www.geeksforgeeks.org/python-counting-nth-tuple-element/)

有时候，在使用 Python 时，我们可能会遇到一个问题，需要计算某个特定元素的出现次数。这种问题在处理记录时很常见。让我们讨论一下执行这项任务的方法。

**方法#1:使用`Counter()` +生成器表达式**
上述功能的组合可用于实现该特定任务。在本文中，我们使用生成器表达式迭代特定的索引，并使用`Counter()`计算计数。

```py
# Python3 code to demonstrate working of
# Counting Nth tuple element
# using Counter() + generator expression
from collections import Counter

# initialize list
test_list = [('gfg', 0), ('is', 1), ('best', 2),
             ('gfg', 2), ('is', 0), ('for', 1),
             ('geeks', 2)]

# printing original list
print("The original list : " + str(test_list))

# initialize N
N = 1

# Counting Nth tuple element
# using Counter() + generator expression
res = dict(Counter(sub[N] for sub in test_list))

# printing result
print("The grouped Nth element frequency is : " + str(res))
```

**Output :**

> 原始列表:[('gfg '，0)、(' is '，1)、(' best '，2)、(' gfg '，2)、(' is '，0)、(' for '，1)、(' geeks '，2)]
> 分组的第 n 个元素频率为:{0: 2，1: 2，2: 3}