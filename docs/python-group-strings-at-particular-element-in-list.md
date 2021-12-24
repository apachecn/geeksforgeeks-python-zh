# Python |将列表中特定元素的字符串分组

> 原文:[https://www . geesforgeks . org/python-group-strings-at-special-in-list 元素/](https://www.geeksforgeeks.org/python-group-strings-at-particular-element-in-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们必须对字符串进行分组，以便在出现特定元素时，对字符串列表进行分组。这可能是日常编程的一个潜在问题。让我们讨论一下解决这个问题的方法。

**方法:使用`groupby()` +列表理解+ lambda**
该任务可以使用以上功能的组合来执行。在这种情况下，我们使用 groupby()对元素进行分组，分组元素逻辑的决定以 lambda 函数的形式完成。

```
# Python3 code to demonstrate working of
# Group strings at particular element in list
# using groupby() + list comprehension + lambda
from itertools import groupby

# initialize lists
test_list = ['gfg', 'is', 'best', 'and', 'is', 'popular']

# printing original list
print("The original list is : " + str(test_list))

# initialize partition element
ele = 'is'

# Group strings at particular element in list
# using groupby() + list comprehension + lambda
res = [list(j) for i, j in groupby(test_list, lambda x:x == ele) if not i]

# printing result
print("Resultant list after grouping : " + str(res))
```

**Output :**

```
The original list is : ['gfg', 'is', 'best', 'and', 'is', 'popular']
Resultant list after grouping : [['gfg'], ['best', 'and'], ['popular']]

```