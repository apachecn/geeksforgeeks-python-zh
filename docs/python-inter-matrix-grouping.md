# Python–内部矩阵分组

> 原文:[https://www.geeksforgeeks.org/python-inter-matrix-grouping/](https://www.geeksforgeeks.org/python-inter-matrix-grouping/)

给定 2 个矩阵，每行 2 个元素，在第一个元素的基础上分组。

> **输入** : test_list1 = [[2，0]，[8，4]，[9，3]]，test_list2 = [[8，1]，[9，7]，[2，10]]
> **输出** : {2: [0，10]，8: [4，1]，9: [3，7]}
> **说明**:映射交叉矩阵后的所有值，2 映射为 0 和 10。
> 
> **输入** : test_list1 = [[8，4]，[9，3]]，test_list2 = [[8，1]，[9，7]]
> **输出** : {8: [4，1]，9: [3，7]}
> **解释**:交叉矩阵映射后的所有值。

**方法#1:使用 defaultdict() +循环**

这是执行这项任务的方法之一。在这种情况下，我们迭代添加这两个列表，然后从相似的元素组成组，并转换为带有值列表的字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Inter Matrix Grouping
# Using defaultdict() + loop
from collections import defaultdict

# initializing lists
test_list1 = [[5, 8], [2, 0], [8, 4], [9, 3]]
test_list2 = [[8, 1], [9, 7], [2, 10], [5, 6]]

# printing original list
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# initializing mapping list 
res = defaultdict(list)

# concatenation matrix using 2 lists
for key, val in test_list1 + test_list2:
    res[key].append(val)

# printing result 
print("The Grouped Matrix : " + str(dict(res)))
```

**Output**

```
The original list 1 : [[5, 8], [2, 0], [8, 4], [9, 3]]
The original list 2 : [[8, 1], [9, 7], [2, 10], [5, 6]]
The Grouped Matrix : {5: [8, 6], 2: [0, 10], 8: [4, 1], 9: [3, 7]}

```

**方法 2:使用词典理解+ dict()**

这是执行这项任务的另一种方式。在本文中，我们通过将两个矩阵的所有元素转换为字典并对其值进行分组来迭代这两个矩阵的所有元素。在两个矩阵中都有每个元素映射的痕迹是很重要的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Inter Matrix Grouping
# Using dictionary comprehension + dict()

# initializing lists
test_list1 = [[5, 8], [2, 0], [8, 4], [9, 3]]
test_list2 = [[8, 1], [9, 7], [2, 10], [5, 6]]

# printing original list
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# mapping dictionaries together, converting each row to dictionary
res = {key: [dict(test_list1)[key], dict(test_list2)[key]] for key in dict(test_list1)}

# printing result 
print("The Grouped Matrix : " + str(dict(res)))
```

**Output**

```
The original list 1 : [[5, 8], [2, 0], [8, 4], [9, 3]]
The original list 2 : [[8, 1], [9, 7], [2, 10], [5, 6]]
The Grouped Matrix : {5: [8, 6], 2: [0, 10], 8: [4, 1], 9: [3, 7]}

```