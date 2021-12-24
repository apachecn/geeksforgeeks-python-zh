# Python |两个列表中的完整性排序

> 原文:[https://www . geesforgeks . org/python-integrity-二选一列表/](https://www.geeksforgeeks.org/python-integrity-sorting-in-two-lists/)

在解决问题的过程中，我们经常会遇到许多需要对列表进行排序的问题。但是有时我们也想对另一个列表进行排序，这样的话，的元素会自动移动，并且即使在第一个列表被排序之后，也保持在与第一个列表相同的索引处。让我们讨论一下实现这一点的某些方法。

**方法一:使用`sorted() + zip() + itemgetter()`**
结合这三个功能，我们有可能完成任务。zip 函数将两个列表绑定在一起，sorted 函数对列表进行排序，itemgetter 函数用于定义我们需要第二个列表移动的指标，在本例中是第一个列表。

```
# Python3 code to demonstrate 
# integrity sorting in two list 
# using sorted() + zip() + itemgetter()
from operator import itemgetter

# initializing lists
test_list1 = [3, 4, 9, 1, 6]
test_list2 = [1, 5, 3, 6, 7]

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using sorted() + zip() + itemgetter()
# integrity sorting in two list 
res = [list(x) for x in zip(*sorted(zip(test_list1, test_list2),
                                         key = itemgetter(0)))]

# printing result 
print ("The lists after integrity sort : " +  str(res))
```

**Output:**

```
The original list 1 is : [3, 4, 9, 1, 6]
The original list 2 is : [1, 5, 3, 6, 7]
The lists after integrity sort : [[1, 3, 4, 6, 9], [6, 1, 5, 7, 3]]

```

**方法#2:使用`sorted() + zip() + lambda function`**
这个方法执行相似的任务，每个函数执行相似的功能，不同的只是代替 itemgetter 函数，lambda 函数执行分配一个基来排序列表的任务，也就是这种情况下的第一个列表。

```
# Python3 code to demonstrate 
# integrity sorting in two list 
# using sorted() + zip() + lambda function
from operator import itemgetter

# initializing lists
test_list1 = [3, 4, 9, 1, 6]
test_list2 = [1, 5, 3, 6, 7]

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using sorted() + zip() + lambda function
# integrity sorting in two list 
res = [list(i) for i in zip(*sorted(zip(test_list1, test_list2),
                                  key = lambda dual: dual[0]))]

# printing result 
print ("The lists after integrity sort : " +  str(res))
```

**Output:**

```
The original list 1 is : [3, 4, 9, 1, 6]
The original list 2 is : [1, 5, 3, 6, 7]
The lists after integrity sort : [[1, 3, 4, 6, 9], [6, 1, 5, 7, 3]]

```