# Python |在列表列表中查找常用元素

> 原文:[https://www . geesforgeks . org/python-find-common-elements-in-list-list/](https://www.geeksforgeeks.org/python-find-common-elements-in-list-of-lists/)

在 2 个列表的列表中找到公共元素的问题是一个相当常见的问题，可以很容易地处理，并且之前也讨论过很多次。但是有时，我们需要从 N 个列表中找到共同的元素。让我们讨论一下执行这个操作的某些方法。

**方法#1:使用`reduce() + lambda + set()`**
结合上述功能，只需一行即可完成该特定任务。这个减少功能可以用来操作&的功能，对所有的列表进行操作。set 函数可用于将列表转换为集合，以消除重复。

```
# Python3 code to demonstrate 
# common element extraction form N lists 
# using reduce() + lambda + set()
from functools import reduce

# initializing list of lists
test_list = [[2, 3, 5, 8], [2, 6, 7, 3], [10, 9, 2, 3]]

# printing original list
print ("The original list is : " + str(test_list))

# common element extraction form N lists
# using reduce() + lambda + set()
res = list(reduce(lambda i, j: i & j, (set(x) for x in test_list)))

# printing result
print ("The common elements from N lists : " + str(res))
```

**Output:**

```
The original list is : [[2, 3, 5, 8], [2, 6, 7, 3], [10, 9, 2, 3]]
The common elements from N lists : [2, 3]

```

**方法 2:使用`map() + intersection()`**
`map` 功能可以使用 set.intersection 功能将待操作的每个列表转换为 set 来执行交集。这是执行这项特殊任务的最优雅的方式。

```
# Python3 code to demonstrate 
# common element extraction form N lists 
# using map() + intersection()

# initializing list of lists
test_list = [[2, 3, 5, 8], [2, 6, 7, 3], [10, 9, 2, 3]]

# printing original list
print ("The original list is : " + str(test_list))

# common element extraction form N lists
# using map() + intersection()
res = list(set.intersection(*map(set, test_list)))

# printing result
print ("The common elements from N lists : " + str(res))
```

**Output:**

```
The original list is : [[2, 3, 5, 8], [2, 6, 7, 3], [10, 9, 2, 3]]
The common elements from N lists : [2, 3]

```