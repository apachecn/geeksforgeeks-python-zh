# Python |自定义列表拆分

> 原文:[https://www.geeksforgeeks.org/python-custom-list-split/](https://www.geeksforgeeks.org/python-custom-list-split/)

开发和有时机器学习应用程序需要以自定义方式将列表拆分成更小的列表，即在必须执行拆分的某些值上。这是一个非常有用的工具。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解+ `zip()`**

把列表理解的力量和`zip()`耦合起来，就可以完成这个任务。在这种情况下，我们压缩列表的开头和结尾，然后在列表到达时继续对其进行切片，并从中剪切出新的列表。

```
# Python3 code to demonstrate 
# to perform custom list split
# using list comprehension + zip()

# initializing string  
test_list = [1, 4, 5, 6, 7, 3, 5, 9, 2, 4]

# initializing split index list 
split_list = [2, 5, 7]

# printing original list
print ("The original list is : " + str(test_list))

# printing original split index list
print ("The original split index list : " + str(split_list))

# using list comprehension + zip()
# to perform custom list split
res = [test_list[i : j] for i, j in zip([0] + 
          split_list, split_list + [None])]

# printing result
print ("The splitted lists are : " +  str(res))
```

**Output:**

```
The original list is : [1, 4, 5, 6, 7, 3, 5, 9, 2, 4]
The original split index list : [2, 5, 7]
The splitted lists are : [[1, 4], [5, 6, 7], [3, 5], [9, 2, 4]]

```

**方法 2:使用`itertools.chain() + zip()`**

获得分割组块的列表理解功能所执行的任务也可以使用链功能来完成。当我们希望处理更大的列表时，这更有用，因为这种方法更有效。

```
# Python3 code to demonstrate 
# to perform custom list split
# using itertools.chain() + zip()
from itertools import chain

# initializing string  
test_list = [1, 4, 5, 6, 7, 3, 5, 9, 2, 4]

# initializing split index list 
split_list = [2, 5, 7]

# printing original list
print ("The original list is : " + str(test_list))

# printing original split index list
print ("The original split index list : " + str(split_list))

# using itertools.chain() + zip()
# to perform custom list split
temp = zip(chain([0], split_list), chain(split_list, [None]))
res = list(test_list[i : j] for i, j in temp)

# printing result
print ("The splitted lists are : " +  str(res))
```

**Output:**

```
The original list is : [1, 4, 5, 6, 7, 3, 5, 9, 2, 4]
The original split index list : [2, 5, 7]
The splitted lists are : [[1, 4], [5, 6, 7], [3, 5], [9, 2, 4]]

```