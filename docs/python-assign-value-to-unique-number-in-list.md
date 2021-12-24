# Python |为列表中的唯一数字赋值

> 原文:[https://www . geesforgeks . org/python-将值赋给列表中唯一的数字/](https://www.geeksforgeeks.org/python-assign-value-to-unique-number-in-list/)

我们可以给列表中的所有数字分配一个唯一的值，在重复时，它会保留保留给它的值。这是一个非常常见的问题，是在网页开发中玩 id 的时候面临的。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`enumerate()` +列表理解**
列表理解可以与枚举功能一起用于执行该特定任务，枚举功能借助于列表中迭代中的集合和前一个帮助来选择唯一的数字。

```
# Python3 code to demonstrate
# assign unique value to list elements
# using list comprehension + enumerate

# initializing list
test_list = [1, 4, 6, 1, 4, 5, 6]

# printing the original list
print ("The original list is : " + str(test_list))

# using list comprehension + enumerate
# assign unique value to list elements 
temp = {i: j for j, i in enumerate(set(test_list))}
res = [temp[i] for i in test_list]

# printing result
print ("The unique value list is : " + str(res))
```

**Output:**

```
The original list is : [1, 4, 6, 1, 4, 5, 6]
The unique value list is : [0, 1, 3, 0, 1, 2, 3]

```

**方法 2:使用`setdefault() + map() + count()`**
这三个功能的组合也可以用来执行这个特定的任务。Map 绑定所有相似的元素，setdefault 为它们分配唯一的数字，count 函数帮助 map 查找总出现次数。

```
# Python3 code to demonstrate
# assign unique value to list elements
# using setdefault() + map() + count()
from itertools import count

# initializing list
test_list = [1, 4, 6, 1, 4, 5, 6]

# printing the original list
print ("The original list is : " + str(test_list))

# using setdefault() + map() + count()
# assign unique value to list elements 
res = list(map({}.setdefault, test_list, count()))

# printing result
print ("The unique value list is : " + str(res))
```

**Output:**

```
The original list is : [1, 4, 6, 1, 4, 5, 6]
The unique value list is : [0, 1, 2, 0, 1, 5, 2]

```