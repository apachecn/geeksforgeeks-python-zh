# Python |为列表中的每个唯一值分配 id

> 原文:[https://www . geeksforgeeks . org/python-为列表中的每个唯一值分配 id/](https://www.geeksforgeeks.org/python-assign-ids-to-each-unique-value-in-a-list/)

有时，在 web 开发领域或竞争性编程中工作时，我们需要为每个不同的值分配一个唯一的 id，以跟踪它的出现次数或任何其他必需的用例。让我们讨论执行这项任务的某些方法。

**方法一:使用`defaultdict`+λ+列表理解**

上述功能的组合可用于完成这一特定任务。defaultdict 函数使用 lambda 函数执行分配 Ids 的主要任务，它为每个新键分配当前的键数。列表理解用于后期形成列表。

```py
# Python3 code to demonstrate
# assigning ids to values
# using list comprehension + defaultdict + lambda
from collections import defaultdict

# initializing list
test_list = [5, 6, 7, 6, 5, 1]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + defaultdict + lambda
# assigning ids to values
temp = defaultdict(lambda: len(temp))
res = [temp[ele] for ele in test_list]

# print result
print("The ids of assigned values is : " + str(res))
```

**Output :**

```py
The original list : [5, 6, 7, 6, 5, 1]
The ids of assigned values is : [0, 1, 2, 1, 0, 3]

```

**方法二:使用`OrderedDict.fromkeys() + enumerate()` +列表理解**

此方法执行的任务类似于上述方法。在这种情况下，orderedDict.fromkeys 函数执行删除重复项的功能，枚举函数帮助我们获取值的索引，以便将它们映射在一起。

```py
# Python3 code to demonstrate
# assigning ids to values using 
# list comprehension + OrderedDict.fromkeys() + enumerate()
from collections import OrderedDict

# initializing list
test_list = [5, 6, 7, 6, 5, 1]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + OrderedDict.fromkeys() + enumerate()
# assigning ids to values
res = [{val : key for key, val in enumerate(
           OrderedDict.fromkeys(test_list))}
                 [ele] for ele in test_list]

# print result
print("The ids of assigned values is : " + str(res))
```

**Output :**

```py
The original list : [5, 6, 7, 6, 5, 1]
The ids of assigned values is : [0, 1, 2, 1, 0, 3]

```