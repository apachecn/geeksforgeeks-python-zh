# Python |访问给定索引列表中的所有元素

> 原文:[https://www . geesforgeks . org/python-访问给定索引列表中的所有元素/](https://www.geeksforgeeks.org/python-accessing-all-elements-at-given-list-of-indexes/)

在 python 中，从一个元素的索引中访问它是一项更简单的任务，只需在列表中使用`[]`操作符就可以了。但是在某些情况下，当我们有不止一个索引时，我们会被呈现任务，并且我们需要获得对应于这些索引的所有元素。让我们讨论完成这项任务的某些方法。

```
Input : list = [9, 4, 5, 8, 10, 14]
        index_list = [1, 3, 4]
Output : 4 8 10

```

**方法#1:使用列表理解**
这个任务很容易循环执行，因此简写为第一个从这个任务开始的方法。迭代索引列表以从列表中获取相应的元素到新列表中是执行这个任务的强力方法。

```
# Python3 code to demonstrate 
# to get elements from indices
# using list comprehension

# initializing lists
test_list = [9, 4, 5, 8, 10, 14]
index_list = [1, 3, 4]

# printing original lists
print ("Original list : " + str(test_list))
print ("Original index list : " + str(index_list))

# using list comprehension to 
# elements from list 
res_list = [test_list[i] for i in index_list]

# printing result
print ("Resultant list : " + str(res_list))
```

**输出:**

```
Original list : [9, 4, 5, 8, 10, 14]
Original index list : [1, 3, 4]
Resultant list : [4, 8, 10]

```

**方法#2:使用`map() + __getitem__`**
实现该特定任务的另一种方法是将一个列表与其他列表进行映射，获取索引项，并从搜索列表中获取相应的匹配元素。这是完成这项任务的快速方法。

```
# Python3 code to demonstrate 
# to get elements from indices
# using map() + __getitem__

# initializing lists
test_list = [9, 4, 5, 8, 10, 14]
index_list = [1, 3, 4]

# printing original lists
print ("Original list : " + str(test_list))
print ("Original index list : " + str(index_list))

# using map() + __getitem__ to 
# elements from list 
res_list = map(test_list.__getitem__, index_list)

# printing result
print ("Resultant list : " + str(res_list))
```

**输出:**

```
Original list : [9, 4, 5, 8, 10, 14]
Original index list : [1, 3, 4]
Resultant list : [4, 8, 10]

```

**方法#3:使用`operator.itemgetter()`**
这种手法是执行这一特定任务的最蟒化、最优雅的方法。这个函数将原始列表中的元素与另一个列表中所需的索引进行压缩，因此是实现这个任务的最快方法。

```
# Python3 code to demonstrate 
# to get elements from indices
# using operator.itemgetter()
from operator import itemgetter

# initializing lists
test_list = [9, 4, 5, 8, 10, 14]
index_list = [1, 3, 4]

# printing original lists
print ("Original list : " + str(test_list))
print ("Original index list : " + str(index_list))

# using operator.itemgetter() to 
# elements from list 
res_list = list(itemgetter(*index_list)(test_list))

# printing result
print ("Resultant list : " + str(res_list))
```

**输出:**

```
Original list : [9, 4, 5, 8, 10, 14]
Original index list : [1, 3, 4]
Resultant list : [4, 8, 10]

```