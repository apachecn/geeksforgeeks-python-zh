# Python |在列表中多次添加相似值

> 原文:[https://www . geesforgeks . org/python-add-相似值-多次列表/](https://www.geeksforgeeks.org/python-add-similar-value-multiple-times-in-list/)

在列表中添加一个值非常简单。但是要多次添加该值，通常使用一个循环来执行该任务。使用更短的技巧来完成这项任务可能会很方便。让我们讨论一下实现这一点的某些方法。

**方法#1:使用*运算符**
我们可以使用*运算符来乘以特定值的出现次数，因此可以用来在一行中多次执行添加值的任务，并使其可读。

```
# Python3 code to demonstrate 
# to add multiple similar values
# using * operator

# using * operator to add multiple values
# adds 3, 50 times.
res = [3] * 50

# printing result
print ("The filtered list is : " + str(res))
```

**输出:**

> 过滤后的列表为:[3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3]

**方法 2:使用`extend()` +列表理解**
扩展功能执行列表追加，列表理解部分负责执行元素所需次数的重复任务。

```
# Python3 code to demonstrate 
# to add multiple similar values
# using extend() + list comprehension

# using extend() + list comprehension to add multiple values
# adds 3, 50 times.
res = []
res.extend([3 for i in range(50)])

# printing result
print ("The filtered list is : " + str(res))
```

**输出:**

> 过滤后的列表为:[3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3]

**方法#3:使用`extend() + itertools.repeat()`**
这类似于上面的方法，`extend()` 的任务类似，但是 `repeat()`执行迭代次数为 N 次的任务列表理解。

```
# Python3 code to demonstrate 
# to add multiple similar values
# using extend() + itertools.repeat()
from itertools import repeat

# using extend() + itertools.repeat() to add multiple values
# adds 3, 50 times.
res = []
res.extend(repeat(3, 50))

# printing result
print ("The filtered list is : " + str(res))
```

**输出:**

> 过滤后的列表为:[3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3，3]