# Python–矩阵中的组元素

> 原文:[https://www . geesforgeks . org/python-group-elements-in-matrix/](https://www.geeksforgeeks.org/python-group-elements-in-matrix/)

给定一个有两列的矩阵，在第一列的基础上分组第二列元素。

> **输入** : test_list = [[5，8]，[2，0]，[5，4]，[2，3]，[2，9]]
> **输出** : {5: [8，4]，2: [0，3，9]}
> **解释** : 8 和 4 在矩阵中映射为 5，其他全部映射为 2。
> 
> **输入** : test_list = [[2，8]，[2，0]，[2，4]，[2，3]，[2，9]]
> **输出** : {2: [8，4，0，3，9]}
> **解释**:全部映射到 2。

**方法一:使用词典理解+循环**

这是执行这项任务的方法之一。在这种情况下，我们用第 1 行的空列表值构造字典，然后运行一个循环向其中赋值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Group Elements in Matrix
# Using dictionary comprehension + loop

# initializing list
test_list = [[5, 8], [2, 0], [5, 4], [2, 3], [7, 9]]

# printing original list
print("The original list : " + str(test_list))

# initializing empty dictionary with default empty list 
res = {idx[0]: [] for idx in test_list}

# using loop for grouping
for idx in test_list:
    res[idx[0]].append(idx[1])

# printing result 
print("The Grouped Matrix : " + str(res))
```

**Output**

```
The original list : [[5, 8], [2, 0], [5, 4], [2, 3], [7, 9]]
The Grouped Matrix : {5: [8, 4], 2: [0, 3], 7: [9]}

```

**方法 2:使用 loop + defaultdict()**

这类似于上面的方法。不同之处在于，初始空网格是使用 defaultdict()创建的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Group Elements in Matrix
# Using loop + defaultdict()
from collections import defaultdict

# initializing list
test_list = [[5, 8], [2, 0], [5, 4], [2, 3], [7, 9]]

# printing original list
print("The original list : " + str(test_list))

# initializing empty dictionary using defaultdict
res = defaultdict(list)

# using loop for grouping
for idx in test_list:
    res[idx[0]].append(idx[1])

# printing result 
print("The Grouped Matrix : " + str(dict(res)))
```

**Output**

```
The original list : [[5, 8], [2, 0], [5, 4], [2, 3], [7, 9]]
The Grouped Matrix : {5: [8, 4], 2: [0, 3], 7: [9]}

```