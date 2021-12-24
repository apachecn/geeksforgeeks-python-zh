# Python–按第 k 个索引元素分组元组

> 原文:[https://www . geesforgeks . org/python-group-元组-by-kth-index-element/](https://www.geeksforgeeks.org/python-group-tuples-by-kth-index-element/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即我们需要通过类似的 Kth 索引元素对元组的元素进行分组。这类问题在 web 开发领域会有应用。让我们讨论一下执行这项任务的具体方法。

> **输入** : test_list = [(4，5)，(3，2)，(2，2)，(1，2)，(5，5)]，K = 0
> **输出**:[(1，2)，(2，2)，)，((3，2)，)，((4，5)，)，((5，5)，)]
> 
> **输入** : test_list = [(4，5)，(3，2)，(2，2)]，K = 1
> **输出**:[(2，2)，(3，2))，((4，5)，]

**方法:使用`groupby() + itemegetter()` +生成器表达式**
以上功能的组合可以解决这个问题。在这种情况下，我们执行对使用 itemgetter 提取的 Kth 索引中的元素进行分组的任务，生成器表达式用于将整个逻辑绑定在一起。

```py
# Python3 code to demonstrate working of 
# Group Tuples by Kth Index Element
# Using groupby() + itemegetter() + generator expression
from operator import itemgetter
from itertools import groupby

# initializing lists
test_list = [(4, 5), (3, 2), (2, 2), (1, 2), (5, 5)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 1

# Group Tuples by Kth Index Element
# Using groupby() + itemegetter() + generator expression
test_list.sort()
res = list(tuple(sub) for idx, sub in groupby(test_list, key = itemgetter(K)))

# printing result 
print("Tuples after grouping : " + str(res))
```

**Output :**

```py
The original list is : [(4, 5), (3, 2), (2, 2), (1, 2), (5, 5)]
Tuples after grouping : [((1, 2), (2, 2), (3, 2)), ((4, 5), (5, 5))]

```