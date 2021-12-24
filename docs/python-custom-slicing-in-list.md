# Python |列表中自定义切片

> 原文:[https://www . geesforgeks . org/python-自定义-列表切片/](https://www.geeksforgeeks.org/python-custom-slicing-in-list/)

有时候，在使用 Python 时，我们会遇到一个需要执行列表切片的问题。列表切片可以有很多变体。可以有自定义切片间隔和切片元素。让我们对这样的问题进行讨论。

**方法:使用`compress() + cycle()`**
以上功能的组合可以用来执行这个特定的任务。在这种情况下，我们过滤列表中所需元素的真值，并通过提供布尔值 false 来消除那些应该跳过的元素。然后使用内置的`compress()`累计结果

```
# Python3 code to demonstrate working of
# Custom slicing in List
# using compress() + cycle()
from itertools import cycle, compress

# initialize lists
test_list = [1, 2, 4, 7, 3, 8, 6, 2, 10, 11, 17, 34, 23, 21]

# printing original list
print("The original list is : " + str(test_list))

# initialize interval
interval = 5

# initialize element number 
ele_num = 4

# Custom slicing in List
# using compress() + cycle()
temp = cycle([True] * ele_num + [False] * interval)
res = list(compress(test_list, temp))

# printing result
print("Custom sliced list is : " + str(res))
```

**Output :**

```
The original list is : [1, 2, 4, 7, 3, 8, 6, 2, 10, 11, 17, 34, 23, 21]
Custom sliced list is : [1, 2, 4, 7, 11, 17, 34, 23]

```