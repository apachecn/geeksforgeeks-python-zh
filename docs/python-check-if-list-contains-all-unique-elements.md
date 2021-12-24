# Python |检查列表是否包含所有唯一元素

> 原文:[https://www . geesforgeks . org/python-check-if-list-contains-all-unique-elements/](https://www.geeksforgeeks.org/python-check-if-list-contains-all-unique-elements/)

有些列表操作要求我们检查列表中的所有元素是否都是唯一的。这通常发生在我们试图执行列表中的 set 操作时。因此，这种特殊的效用在这些时候是必不可少的。让我们讨论一下可以执行此操作的某些方法。

**方法#1:天真的方法**
解决方案通常从一个人可以用来执行特定任务的最简单的方法开始。在这里，您可以使用嵌套循环来检查在该元素之后，在剩余的列表中是否存在类似的元素。

```
# Python3 code to demonstrate 
# to test all elements in list are unique
# using naive method 

# initializing list 
test_list = [1, 3, 4, 6, 7]

# printing original list 
print ("The original list is : " + str(test_list))

flag = 0

# using naive method 
# to check all unique list elements
for i in range(len(test_list)):
        for i1 in range(len(test_list)):
            if i != i1:
                if test_list[i] == test_list[i1]:
                    flag = 1

# printing result
if(not flag) :
    print ("List contains all unique elements")
else : 
    print ("List contains does not contains all unique elements")
```

**输出:**

```
The original list is : [1, 3, 4, 6, 7]
List contains all unique elements

```

**方法 2:使用`len() + set()`**
这是只用一条线就能解决这个问题的最优雅的方式。此解决方案将列表转换为集合，然后用原始列表测试是否包含相似数量的元素。

```
# Python3 code to demonstrate 
# to test all elements in list are unique
# using set() + len()

# initializing list 
test_list = [1, 3, 4, 6, 7]

# printing original list 
print ("The original list is : " + str(test_list))

flag = 0

# using set() + len()
# to check all unique list elements
flag = len(set(test_list)) == len(test_list)

# printing result
if(flag) :
    print ("List contains all unique elements")
else : 
    print ("List contains does not contains all unique elements")
```

**输出:**

```
The original list is : [1, 3, 4, 6, 7]
List contains all unique elements

```

**方法#3:使用`Counter.itervalues()`**
这是不同的方法之一，使用使用 Counter 获得的所有元素的频率，并检查是否有任何频率大于 1。

```
# Python code to demonstrate 
# to test all elements in list are unique
# using Counter.itervalues()
from collections import Counter

# initializing list 
test_list = [1, 3, 4, 6, 7]

# printing original list 
print ("The original list is : " + str(test_list))

flag = 0

# using Counter.itervalues() 
# to check all unique list elements
counter = Counter(test_list)
for values in counter.itervalues():
        if values > 1:
            flag = 1

# printing result
if(not flag) :
    print ("List contains all unique elements")
else : 
    print ("List contains does not contains all unique elements")
```

**输出:**

```
The original list is : [1, 3, 4, 6, 7]
List contains all unique elements

```