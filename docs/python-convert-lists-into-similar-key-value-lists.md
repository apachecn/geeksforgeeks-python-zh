# Python–将列表转换为相似的键值列表

> 原文:[https://www . geesforgeks . org/python-convert-list-to-like-key-value-list/](https://www.geeksforgeeks.org/python-convert-lists-into-similar-key-value-lists/)

给定两个列表，一个是键，另一个是值，将其转换为带有列表值的字典，如果键根据索引映射到不同的值，则将其添加到值列表中。

> **输入** : test_list1 = [5，6，6，6]，test_list2 = [8，3，2，9]
> **输出** : {5: [8]，6: [3，2，9]}
> **解释**:对应列表中索引为 6 的元素，映射为 6。
> 
> **输入** : test_list1 = [6，6，6，6]，test_list2 = [8，3，2，9]
> **输出** : {6: [8，3，2，9]}
> **解释**:全部映射到单个数字。

**方法一:使用 zip() + loop**

这是执行这项任务的方法之一。在本例中，我们使用 zip()将键映射到所需的值，并使用循环来执行键的迭代。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert Lists into Similar key value lists
# Using loop + zip()

# initializing lists
test_list1 = [5, 6, 6, 4, 5, 6] 
test_list2 = [8, 3, 2, 9, 10, 4]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# creating a mesh of keys with empty values list
res = {key: [] for key in test_list1}

# loop to iterate through keys and values
for key, val in zip(test_list1, test_list2):
    res[key].append(val)

# printing result 
print("The mapped dictionary : " + str(res)) 
```

**Output**

```py
The original list 1 is : [5, 6, 6, 4, 5, 6]
The original list 2 is : [8, 3, 2, 9, 10, 4]
The mapped dictionary : {5: [8, 10], 6: [3, 2, 4], 4: [9]}

```

**方法 2:使用 defaultdict() +列表理解+ zip()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们作为一个线性函数执行任务，defaultdict()用于预分配空列表的值。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Convert Lists into Similar key value lists
# Using defaultdict() + list comprehension + zip()
from collections import defaultdict

# initializing lists
test_list1 = [5, 6, 6, 4, 5, 6] 
test_list2 = [8, 3, 2, 9, 10, 4]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# creating a mesh of keys using defaultdict
res = defaultdict(list)
[res[key].append(val) for key, val in zip(test_list1, test_list2)]

# printing result 
print("The mapped dictionary : " + str(dict(res))) 
```

**Output**

```py
The original list 1 is : [5, 6, 6, 4, 5, 6]
The original list 2 is : [8, 3, 2, 9, 10, 4]
The mapped dictionary : {5: [8, 10], 6: [3, 2, 4], 4: [9]}

```