# Python–通过元组列表中的第二个元素对第一个元素进行分组

> 原文:[https://www . geesforgeks . org/python-group-first-elements-by-second-elements-in-tuple-list/](https://www.geeksforgeeks.org/python-group-first-elements-by-second-elements-in-tuple-list/)

给定元组列表，在第二个元素的基础上分组第一个元素。

> **输入** : test_list = [(6，5)，(2，7)，(2，5)，(8，7)，(3，7)]
> **输出** : {5: [6，2]，7: [2，8，3]}
> **解释** : 5 与元组列表中的 6 和 2 一起出现，因此分组。
> 
> **输入** : test_list = [(6，5)，(2，7)，(2，5)，(8，7)]
> **输出** : {5: [6，2]，7: [2，8]}
> **解释** : 5 与元组列表中的 6 和 2 一起出现，因此分组。

**方法一:使用 loop + groupby() + sorted() +列表理解+ lambda**

在这种情况下，对元素进行分组排序，函数由 lambda 提供，然后使用列表理解从结果中仅提取第一个元素。和使用循环的最终字典形成。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Group first elements by second elements in Tuple list
# Using loop + groupby() + sorted() + list comprehension + lambda
from itertools import groupby

# initializing list
test_list = [(6, 5), (2, 7), (2, 5), (8, 7), (9, 8), (3, 7)]

# printing original list
print("The original list is : " + str(test_list))

res = dict()

# forming equal groups
for key, val in groupby(sorted(test_list, key = lambda ele: ele[1]), key = lambda ele: ele[1]):
    res[key] = [ele[0] for ele in val] 

# printing results
print("Grouped Dictionary : " + str(res))
```

**Output**

```py
The original list is : [(6, 5), (2, 7), (2, 5), (8, 7), (9, 8), (3, 7)]
Grouped Dictionary : {5: [6, 2], 7: [2, 8, 3], 8: [9]}

```

**方法二:利用词典理解**

这是类似于上面的方法，只是使用字典理解处理的一行速记。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Group first elements by second elements in Tuple list
# Using dictionary comprehension 
from itertools import groupby

# initializing list
test_list = [(6, 5), (2, 7), (2, 5), (8, 7), (9, 8), (3, 7)]

# printing original list
print("The original list is : " + str(test_list))

# shorthand to solve problem
res = {key : [v[0] for v in val] for key, val in groupby(sorted(test_list, key = lambda ele: ele[1]), key = lambda ele: ele[1])}

# printing results
print("Grouped Dictionary : " + str(res))
```

**Output**

```py
The original list is : [(6, 5), (2, 7), (2, 5), (8, 7), (9, 8), (3, 7)]
Grouped Dictionary : {5: [6, 2], 7: [2, 8, 3], 8: [9]}

```