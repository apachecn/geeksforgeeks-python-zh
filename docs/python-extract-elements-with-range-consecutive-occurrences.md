# Python–提取范围连续出现的元素

> 原文:[https://www . geesforgeks . org/python-extract-elements-with-range-continuous-occurs/](https://www.geeksforgeeks.org/python-extract-elements-with-range-consecutive-occurrences/)

有时在处理数据时，我们可能会遇到这样的问题:我们需要选择一些连续出现的元素。这个问题可能发生在许多领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`groupby()` +列表理解**
该任务可以使用上述功能执行。在这种情况下，我们将连续出现的所有数字分组。我们使用列表理解来迭代列表。

```py
# Python3 code to demonstrate working of
# Extract elements with Range consecutive occurrences
# using groupby() + list comprehension
from itertools import groupby

# initialize list 
test_list = [1, 1, 4, 5, 5, 6, 7, 7, 7, 8, 8, 8, 8]

# printing original list 
print("The original list : " + str(test_list))

# initialize strt, end 
strt, end = 2, 3

# Extract elements with Range consecutive occurrences
# using groupby() + list comprehension
res1 = [i for i, j in groupby(test_list) if len(list(j)) <= end]
res2 = [i for i, j in groupby(test_list) if len(list(j)) >= strt]
res = list(set(res1) & set(res2))

# printing result
print("The range consecutive elements are : " + str(res))
```

**Output :**

```py
The original list : [1, 1, 4, 5, 5, 6, 7, 7, 7, 8, 8, 8, 8]
The range consecutive elements are : [1, 5, 7]

```