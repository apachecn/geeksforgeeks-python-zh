# Python |列表中的元素重复

> 原文:[https://www . geesforgeks . org/python-element-repeat-in-list/](https://www.geeksforgeeks.org/python-element-repetition-in-list/)

有时我们需要在列表中为几个不同的实用程序添加一个重复的值。这种类型的应用程序在日常编程中有时是必需的。让我们讨论一下将一个数字的克隆添加到下一个位置的某些方法。

**方法#1:使用列表理解**
在这个方法中，我们只需对每个值重复循环两次，并添加到所需的新列表中。这只是简单方法的一种替代。

```
# Python3 code to demonstrate 
# to perform element duplication
# using list comprehension

# initializing list  
test_list = [4, 5, 6, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# using list comprehension
# to perform element duplication
res = [i for i in test_list for x in (0, 1)]

# printing result 
print ("The list after element duplication " +  str(res))
```

**输出:**

```
The original list is : [4, 5, 6, 3, 9]
The list after element duplication [4, 4, 5, 5, 6, 6, 3, 3, 9, 9]

```

**方法 2:使用 **reduce() + add****
我们还可以使用 reduce 函数来充当函数，在列表中同时执行一对相似数字的加法。

```
# Python3 code to demonstrate 
# to perform element duplication
# using reduce() + add
from operator import add

# initializing list  
test_list = [4, 5, 6, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# using reduce() + add
# to perform element duplication
res = list(reduce(add, [(i, i) for i in test_list]))

# printing result 
print ("The list after element duplication " +  str(res))
```

**输出:**

```
The original list is : [4, 5, 6, 3, 9]
The list after element duplication [4, 4, 5, 5, 6, 6, 3, 3, 9, 9]

```

**方法 3:使用`itertools.chain().from_iterable()`**
from_iterable 函数也可以执行这个添加副本的任务。它只是生成每个迭代元素的对，并将其连续插入。

```
# Python3 code to demonstrate 
# to perform element duplication
# using itertools.chain.from_iterable()
import itertools

# initializing list  
test_list = [4, 5, 6, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# using itertools.chain.from_iterable()
# to perform element duplication
res = list(itertools.chain.from_iterable([i, i] for i in test_list))

# printing result 
print ("The list after element duplication " +  str(res))
```

**输出:**

```
The original list is : [4, 5, 6, 3, 9]
The list after element duplication [4, 4, 5, 5, 6, 6, 3, 3, 9, 9]

```