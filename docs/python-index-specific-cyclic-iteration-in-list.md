# Python |列表中特定于索引的循环迭代

> 原文:[https://www . geesforgeks . org/python-index-specific-cycle-iteration-in-list/](https://www.geeksforgeeks.org/python-index-specific-cyclic-iteration-in-list/)

循环迭代的问题很常见，但有时，我们会遇到这样的问题，即我们需要以循环迭代的方式处理列表，也就是从特定的索引开始。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`%` 运算符+循环**
可以使用%运算符循环超出界限的索引值，从列表的开头开始形成循环，从而有助于循环迭代。

```
# Python3 code to demonstrate 
# cyclic iteration in list 
# using % operator and loop

# initializing tuple list 
test_list = [5, 4, 2, 3, 7]

# printing original list
print ("The original list is : " + str(test_list))

# starting index 
K = 3

# using % operator and loop
# cyclic iteration in list 
res = []
for i in range(len(test_list)):
    res.append(test_list[K % len(test_list)])
    K = K + 1

# printing result 
print ("The cycled list is : " +  str(res))
```

**Output:**

```
The original list is : [5, 4, 2, 3, 7]
The cycled list is : [3, 7, 5, 4, 2]

```

**方法 2:使用`itertools.cycle() + itertools.islice() + itertools.dropwhile()`**
ITER tools 库内置了一些函数，可以帮助解决这个特定的问题。循环功能执行循环部分，dropwhile 功能使循环从列表开始，islice 功能指定循环大小。

```
# Python3 code to demonstrate 
# cyclic iteration in list using itertools
from itertools import cycle, islice, dropwhile

# initializing tuple list 
test_list = [5, 4, 2, 3, 7]

# printing original list
print ("The original list is : " + str(test_list))

# starting index 
K = 3

# using itertools methods for
# cyclic iteration in list 
cycling = cycle(test_list)  
skipping = dropwhile(lambda x: x != K, cycling) 
slicing = islice(skipping, None, len(test_list))
slicing = list(slicing)

# printing result 
print ("The cycled list is : " +  str(slicing))
```

**Output:**

```
The original list is : [5, 4, 2, 3, 7]
The cycled list is : [3, 7, 5, 4, 2]

```