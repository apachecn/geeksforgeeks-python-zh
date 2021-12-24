# Python |列表元素排序列表的索引

> 原文:[https://www . geesforgeks . org/python-indexs-of-sorted-list-of-list-elements/](https://www.geeksforgeeks.org/python-indices-of-sorted-list-of-list-elements/)

排序是一种常见的构造，已经讨论了它的许多变体。但是有时候，我们需要对列表的列表进行排序，而且只需要在排序之前找到元素出现的*顺序。让我们来看看如何在列表中获得排序顺序的索引。*

**方法#1:使用列表理解+ `enumerate() + sort()`**

以上 3 个功能的组合可用于执行这一特定任务。在这种情况下，我们使用由元素、行和列坐标组成的三元组执行排序，并在第二步中返回它们。

```
# Python3 code to demonstrate
# Indices of sorted list of list elements
# using List comprehension + enumerate() + sort()

# initializing list
test_list = [[4, 5, 1],
             [9, 3, 2],
             [8, 6]]

# printing original list
print("The original list : " + str(test_list))

# using List comprehension + enumerate() + sort()
# Indices of sorted list of list elements
res = [(i, j) for i, x in enumerate(test_list)
                     for j, k in enumerate(x)]

res.sort(key = lambda ij: test_list[ij[0]][ij[1]]) 

# print result
print("The indices of sorted order are : " + str(res))
```

**Output :**

> 原列表:[[4，5，1]，[9，3，2]，[8，6]]
> 排序顺序的索引为:[(0，2)，(1，2)，(1，1)，(0，0)，(0，1)，(2，1)，(2，0)，(1)，(2，0)，(1)，(1，0)]

**方法 2:使用`sorted()`+λ**

上面执行的任务可以作为排序函数的参数来执行，lambda 函数如上执行列表理解函数的任务。

```
# Python3 code to demonstrate
# Indices of sorted list of list elements
# using sorted() + lambda

# initializing list
test_list = [[4, 5, 1],
             [9, 3, 2],
             [8, 6]]

# printing original list
print("The original list : " + str(test_list))

# using sorted() + lambda
# Indices of sorted list of list elements
res = sorted([(i, j) for i, x in enumerate(test_list)
                            for j, k in enumerate(x)],
             key = lambda ij: test_list[ij[0]][ij[1]])

# print result
print("The indices of sorted order are : " + str(res))
```

**Output :**

> 原列表:[[4，5，1]，[9，3，2]，[8，6]]
> 排序顺序的索引为:[(0，2)，(1，2)，(1，1)，(0，0)，(0，1)，(2，1)，(2，0)，(1)，(2，0)，(1)，(1，0)]