# Python |划分两个列表

> 原文:[https://www.geeksforgeeks.org/python-dividing-two-lists/](https://www.geeksforgeeks.org/python-dividing-two-lists/)

有时我们会遇到这样的情况，我们需要对两个相似索引的列表的每个元素应用一个特定的函数。其中最受欢迎的是 4 的初等数学运算。这些非常相似，是作为某些实用程序的应用程序出现的。让我们讨论两个列表划分的某些方式。

**方法#1:使用`zip()` +列表理解**
可以使用 zip 操作将一个列表与另一个列表链接起来，并且计算部分可以由列表理解来处理，因此提供了这个特定问题的简写。

```py
# Python3 code to demonstrate 
# division of lists
# using zip() + list comprehension

# initializing lists 
test_list1 = [3, 5, 2, 6, 4]
test_list2 = [7, 3, 4, 1, 5]

# printing original lists 
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# division of lists
# using zip() + list comprehension
res = [i / j for i, j in zip(test_list1, test_list2)]

# printing result
print ("The division list is : " + str(res))
```

**Output:**

```py
The original list 1 is : [3, 5, 2, 6, 4]
The original list 2 is : [7, 3, 4, 1, 5]
The division list is : [0.42857142857142855, 1.6666666666666667, 0.5, 6.0, 0.8]

```

**方法#2:使用`map()`**
使用地图函数是最优雅的方式，在这种方式下，我们可以将一个函数与两个列表进行孪生。除了除法之外，不同的操作也可以应用于它。

```py
# Python3 code to demonstrate 
# division of lists
# using map()
from operator import truediv

# initializing lists 
test_list1 = [3, 5, 2, 6, 4]
test_list2 = [7, 3, 4, 1, 5]

# printing original lists 
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# division of lists
# using map()
res = list(map(truediv, test_list1, test_list2))

# printing result
print ("The division list is : " + str(res))
```

**Output:**

```py
The original list 1 is : [3, 5, 2, 6, 4]
The original list 2 is : [7, 3, 4, 1, 5]
The division list is : [0.42857142857142855, 1.6666666666666667, 0.5, 6.0, 0.8]

```