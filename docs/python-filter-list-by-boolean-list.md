# Python |通过布尔列表过滤列表

> 原文:[https://www . geesforgeks . org/python-filter-list-by-boolean-list/](https://www.geeksforgeeks.org/python-filter-list-by-boolean-list/)

有时候，在使用 Python 列表时，我们会遇到一个问题，那就是我们必须过滤一个列表。这有时会有变化。一种这样的变化可以是通过使用布尔列表进行过滤。让我们讨论一下完成这项任务的方法。

**方法:使用`itertools.compress()`**
执行此特定任务的最优雅和简单的方法是使用 compress()的内置功能从列表中过滤出所有元素，这些元素相对于其他列表的索引位于 true 位置。

```py
# Python3 code to demonstrate working of
# Filter list by Boolean list
# Using itertools.compress
from itertools import compress

# initializing list
test_list = [6, 4, 8, 9, 10]

# printing list
print("The original list : " + str(test_list))

# initializing Boolean list
bool_list = [True, False, False, True, True]

# printing boolean list 
print("The bool list is : " + str(bool_list))

# Filter list by Boolean list
# Using itertools.compress
res = list(compress(test_list, bool_list))

# Printing result
print("List after filtering is : " + str(res))
```

**Output :**

```py

The original list : [6, 4, 8, 9, 10]
The bool list is : [True, False, False, True, True]
List after filtering is : [6, 9, 10]

```