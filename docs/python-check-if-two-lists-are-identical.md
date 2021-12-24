# Python |检查两个列表是否相同

> 原文:[https://www . geesforgeks . org/python-检查两个列表是否相同/](https://www.geeksforgeeks.org/python-check-if-two-lists-are-identical/)

本文的任务是检查两个无序列表是否在完全相似的位置包含完全相似的元素，即检查两个列表是否完全相等。这是一个非常有用的工具，可以在日常编程中使用。

**方法一:使用`list.sort()``==`算子**
`sort()`再配合 `==`算子即可完成此任务。我们首先对列表进行排序，这样如果两个列表相同，那么它们在相同的位置有元素。但是这没有考虑列表中元素的顺序。

```py
# Python 3 code to demonstrate 
# check if list are identical
# using sort() + == operator

# initializing lists 
test_list1 = [1, 2, 4, 3, 5]
test_list2 = [1, 2, 4, 3, 5]

# printing lists
print ("The first list is : " + str(test_list1))
print ("The second list is : " + str(test_list2))

# sorting both the lists
test_list1.sort()
test_list2.sort()

# using == to check if 
# lists are equal
if test_list1 == test_list2:
    print ("The lists are identical")
else :
    print ("The lists are not identical")
```

**输出:**

```py
The first list is : [1, 2, 4, 3, 5]
The second list is : [1, 2, 4, 3, 5]
The lists are identical

```

**方法二:使用`collections.Counter()`**
使用`Counter()`，我们通常能够得到列表中每个元素的出现频率，对其进行检查，对于两个列表，我们可以检查两个列表是否相同。但是这种方法也忽略了列表中元素的顺序，只考虑了元素的出现频率。

```py
# Python 3 code to demonstrate 
# check if list are identical
# using collections.Counter()
import collections

# initializing lists 
test_list1 = [1, 2, 4, 3, 5]
test_list2 = [1, 2, 4, 3, 5]

# printing lists
print ("The first list is : " + str(test_list1))
print ("The second list is : " + str(test_list2))

# using collections.Counter() to check if 
# lists are equal
if collections.Counter(test_list1) == collections.Counter(test_list2):
    print ("The lists are identical")
else :
    print ("The lists are not identical")
```

**输出:**

```py
The first list is : [1, 2, 4, 3, 5]
The second list is : [1, 2, 4, 3, 5]
The lists are identical

```

**方法三:使用`sum() + zip() + len()`**
使用`sum() + zip()`，如果两个列表中的索引都有相等的元素，我们可以将其中一个列表的和作为 1 的和，然后将该数与其他列表的大小进行比较。这也要求在计算之前首先检查两个列表是否相等。它还会检查订单。

```py
# Python 3 code to demonstrate 
# check if list are identical
# using sum() + zip() + len()

# initializing lists 
test_list1 = [1, 2, 4, 3, 5]
test_list2 = [1, 2, 4, 3, 5]

# printing lists
print ("The first list is : " + str(test_list1))
print ("The second list is : " + str(test_list2))

# using sum() + zip() + len() to check if 
# lists are equal
if len(test_list1)== len(test_list2) and len(test_list1) == sum([1 for i, j in zip(test_list1, test_list2) if i == j]):
    print ("The lists are identical")
else :
    print ("The lists are not identical")
```

**输出:**

```py
The first list is : [1, 2, 4, 3, 5]
The second list is : [1, 2, 4, 3, 5]
The lists are identical

```

**方法四:利用`reduce() + map()`**
将`map()` 的功率与`reduce()`的哈希值和效用仔细耦合，就可以实现检查两个列表是否相等相同的任务。这也考虑了列表的顺序。

```py
# Python 3 code to demonstrate 
# check if list are identical
# using map() + reduce()
import functools

# initializing lists 
test_list1 = [1, 2, 4, 3, 5]
test_list2 = [1, 2, 4, 3, 5]

# printing lists
print ("The first list is : " + str(test_list1))
print ("The second list is : " + str(test_list2))

# using map() + reduce() to check if 
# lists are equal
if functools.reduce(lambda i, j : i and j, map(lambda m, k: m == k, test_list1, test_list2), True) : 
    print ("The lists are identical")
else :
    print ("The lists are not identical")
```

**输出:**

```py
The first list is : [1, 2, 4, 3, 5]
The second list is : [1, 2, 4, 3, 5]
The lists are identical

```