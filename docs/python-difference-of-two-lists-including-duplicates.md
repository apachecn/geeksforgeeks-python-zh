# Python |包含重复的两个列表的区别

> 原文:[https://www . geesforgeks . org/python-两个列表之差-包括重复项/](https://www.geeksforgeeks.org/python-difference-of-two-lists-including-duplicates/)

找到两个列表的[差异的方法已经在前面讨论过了，但是有时，我们要求只移除元素在其他列表中出现的特定情况。让我们讨论一下实现这一点的某些方法。](https://www.geeksforgeeks.org/python-difference-two-lists/)

**方法#1:使用`collections.Counter()`**
计数器方法可用于获取列表中元素的确切出现次数，因此可以选择性地减去，而不是使用集合并完全忽略元素的计数。然后可以执行减法来获得实际的发生。

```
# Python3 code to demonstrate
# Difference of list including duplicates
# Using collections.Counter()
from collections import Counter

# initializing lists
test_list1 = [1, 3, 4, 5, 1, 3, 3]
test_list2 = [1, 3, 5]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Using collections.Counter()
# Difference of list including duplicates
res = list((Counter(test_list1) - Counter(test_list2)).elements())

# print result
print("The list after performing the subtraction : " + str(res))
```

**Output :**

```
The original list 1 : [1, 3, 4, 5, 1, 3, 3]
The original list 2 : [1, 3, 5]
The list after performing the subtraction : [1, 3, 3, 4]

```