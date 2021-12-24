# Python |合并两个排序列表

> 原文:[https://www . geesforgeks . org/python-组合-两个排序列表/](https://www.geeksforgeeks.org/python-combining-two-sorted-lists/)

很多时候，我们遇到一个问题，我们希望使用合并排序的合并函数，这是一个经典的问题，在进行竞争性编程时会多次出现。这种类型的问题，当已知更短和紧凑的方式来执行它们时，总是非常方便。

让我们讨论 Python 中组合两个排序列表的某些方法。

**方法#1:天真方法**

合并排序的合并操作可以使用前面也讨论过的朴素方法来执行。我们检查当前索引中两个元素中较小的一个，并增加遇到编号的列表的索引。当两个列表中的任何一个用完时，另一个列表将被附加到合并列表的末尾。

```
# Python3 code to demonstrate 
# to combine two sorted list 
# using naive method 

# initializing lists
test_list1 = [1, 5, 6, 9, 11]
test_list2 = [3, 4, 7, 8, 10]

# printing original lists 
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using naive method 
# to combine two sorted lists
size_1 = len(test_list1)
size_2 = len(test_list2)

res = []
i, j = 0, 0

while i < size_1 and j < size_2:
    if test_list1[i] < test_list2[j]:
      res.append(test_list1[i])
      i += 1

    else:
      res.append(test_list2[j])
      j += 1

res = res + test_list1[i:] + test_list2[j:]

# printing result
print ("The combined sorted list is : " + str(res))
```

**Output:**

```
The original list 1 is : [1, 5, 6, 9, 11]
The original list 2 is : [3, 4, 7, 8, 10]
The combined sorted list is : [1, 3, 4, 5, 6, 7, 8, 9, 10, 11]

```

**方法 2:使用`sorted()`**

这个函数可以用来在一行中执行这个任务，但是在内部需要更多的时间。当我们将一个列表附加到另一个列表并再次对结果列表进行排序时，可能会有更多的时间复杂性。如果我们需要节省编码时间，应该使用。

```
# Python3 code to demonstrate 
# to combine two sorted list 
# using sorted() 

# initializing lists
test_list1 = [1, 5, 6, 9, 11]
test_list2 = [3, 4, 7, 8, 10]

# printing original lists 
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using sorted()
# to combine two sorted lists
res = sorted(test_list1 + test_list2)

# printing result
print ("The combined sorted list is : " + str(res))
```

**Output:**

```
The original list 1 is : [1, 5, 6, 9, 11]
The original list 2 is : [3, 4, 7, 8, 10]
The combined sorted list is : [1, 3, 4, 5, 6, 7, 8, 9, 10, 11]

```

**方法三:使用`heapq.merge()`**

Python 还提供了执行这一特定任务的内置函数，并在后台执行与朴素方法中的合并类似的工作，应该在想要处理这类问题时使用。

```
# Python3 code to demonstrate 
# to combine two sorted list 
# using heapq.merge()
from heapq import merge

# initializing lists
test_list1 = [1, 5, 6, 9, 11]
test_list2 = [3, 4, 7, 8, 10]

# printing original lists 
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# using heapq.merge()
# to combine two sorted lists
res = list(merge(test_list1, test_list2))

# printing result
print ("The combined sorted list is : " + str(res))
```

**Output:**

```
The original list 1 is : [1, 5, 6, 9, 11]
The original list 2 is : [3, 4, 7, 8, 10]
The combined sorted list is : [1, 3, 4, 5, 6, 7, 8, 9, 10, 11]

```