# Python–过滤两个列表对应相同索引的不等元素

> 原文:[https://www . geesforgeks . org/python-filter-不相等-两个列表的元素-对应-相同-index/](https://www.geeksforgeeks.org/python-filter-unequal-elements-of-two-lists-corresponding-same-index/)

有时，在使用 Python 数据时，我们可能会遇到一个问题，即我们需要跨多个不相等且具有相似索引的列表提取值。这种问题可能出现在许多领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 loop + `zip()`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 zip 提取并组合索引元素，然后使用循环中的条件语句提取并检查相异度。

```
# Python3 code to demonstrate working of
# Unequal Equi-index elements
# using loop + zip()

# initialize lists
test_list1 = ["a", "b", "c", "d"]
test_list2 = ["g", "b", "s", "d"]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Unequal Equi-index elements
# using loop + zip()
res = []
for i, j in zip(test_list1, test_list2):
    if i != j:
        res.append(i)

# printing result
print("Unequal index elements in lists : " + str(res))
```

**Output :**

```
The original list 1 : ['a', 'b', 'c', 'd']
The original list 2 : ['g', 'b', 's', 'd']
Unequal index elements in lists : ['a', 'c']

```