# Python |一次追加多个列表

> 原文:[https://www . geesforgeks . org/python-append-multi-list-at-once/](https://www.geeksforgeeks.org/python-append-multiple-lists-at-once/)

应用程序可能要求将 2-3 个列表的元素附加到一个列表中。这种应用有可能进入机器学习领域，有时也可能进入网络开发领域。让我们讨论一下执行这项特殊任务的某些方法。

**方法#1:使用+运算符**
这可以很容易地使用+运算符来完成，因为它在列表的后面进行元素添加。类似的逻辑在多个列表的情况下被扩展。

## 蟒蛇 3

```
# Python3 code to demonstrate
# adding multiple list at once
# using + operator

# initializing lists
test_list1 = [1, 3, 5, 5, 4]
test_list2 = [4, 6, 2, 8, 10]
test_list3 = [7, 5, 2, 9, 11]

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))
print ("The original list 3 is : " + str(test_list3))

# using + operator
# adding multiple list at once
test_list1 = test_list1 + test_list2 + test_list3

# printing result
print ("The extended and modified list is : " +  str(test_list1))
```

**输出:**

```
The original list 1 is : [1, 3, 5, 5, 4]
The original list 2 is : [4, 6, 2, 8, 10]
The original list 3 is : [7, 5, 2, 9, 11]
The extended and modified list is : [1, 3, 5, 5, 4, 4, 6, 2, 8, 10, 7, 5, 2, 9, 11]
```

**方法#2:使用 itertools.chain()**
链函数也可以用来执行这个特定的任务，因为它使用迭代器来执行这个任务，因此比上述方法提供了更好的性能。

## 蟒蛇 3

```
# Python3 code to demonstrate
# adding multiple list at once
# using itertools.chain()
from itertools import chain

# initializing lists
test_list1 = [1, 3, 5, 5, 4]
test_list2 = [4, 6, 2, 8, 10]
test_list3 = [7, 5, 2, 9, 11]

# printing original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))
print ("The original list 3 is : " + str(test_list3))

# using itertools.chain()
# adding multiple list at once
test_list1 = list(chain(test_list1, test_list2, test_list3))

# printing result
print ("The extended and modified list is : " +  str(test_list1))
```

**输出:**

```
The original list 1 is : [1, 3, 5, 5, 4]
The original list 2 is : [4, 6, 2, 8, 10]
The original list 3 is : [7, 5, 2, 9, 11]
The extended and modified list is : [1, 3, 5, 5, 4, 4, 6, 2, 8, 10, 7, 5, 2, 9, 11]
```