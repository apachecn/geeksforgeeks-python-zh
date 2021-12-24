# Python |检查给定列表列表中是否存在列表

> 原文:[https://www . geesforgeks . org/python-检查列表中是否存在给定列表/](https://www.geeksforgeeks.org/python-check-if-a-list-exists-in-given-list-of-lists/)

给定列表列表，任务是检查给定列表列表中是否存在列表。

```
Input :
lst = [[1, 1, 1, 2], [2, 3, 4], [1, 2, 3], [4, 5, 6]]
list_search = [4, 5, 6]

Output:  True

Input :
lst = [[5, 6, 7], [12, 54, 9], [1, 2, 3]]
list_search = [4, 12, 54]

Output:  False

```

让我们讨论执行这项任务的某些方式。

**方法#1:使用*计数器***
查找列表列表中是否存在列表最简洁易读的方法是使用计数器。

```
# Python code find whether a list 
# exists in list of list.
import collections

# Input List Initialization
Input = [[1, 1, 1, 2], [2, 3, 4], [1, 2, 3], [4, 5, 6]]

# List to be searched
list_search = [2, 3, 4]

# Flag initialization
flag = 0 

# Using Counter
for elem in Input:
    if collections.Counter(elem) == collections.Counter(list_search) :
        flag = 1

# Check whether list exists or not.    
if flag == 0:
    print("False")
else:
    print("True")
```

**Output:**

```
True

```

**方法 2:在** 中使用

```
*# Python code find whether a list 
# exists in list of list.

# Input List Initialization
Input = [[1, 1, 1, 2], [2, 3, 4], [1, 2, 3], [4, 5, 6]]

# List to be searched
list_search = [1, 1, 1, 2]

# Using in to find whether 
# list exists or not
if list_search in Input:
    print("True")
else:
    print("False")*
```

***Output:**

```
True

```* 

 ***方法三:使用`any`***

```
*# Python code find whether a list 
# exists in list of list.

# Input List Initialization
Input = [[1, 1, 1, 2], [2, 3, 4], [1, 2, 3], [4, 5, 6]]

# List to be searched
list_search = [4, 5, 6]

# Using any to find whether 
# list exists or not
if any(list == list_search for list in Input):
    print("True")
else:
    print("False")
     *
```

***Output:**

```
True

```*