# Python–将矩阵转换为重叠元组对

> 原文:[https://www . geesforgeks . org/python-convert-matrix-to-overlap-tuple-pairs/](https://www.geeksforgeeks.org/python-convert-matrix-to-overlapping-tuple-pairs/)

有时，在处理 Python 数据时，我们会遇到一个问题，即我们需要对 Matrix 中的元素进行重叠，并将它们转换为元组对。这种问题可能出现在数据领域的各种应用中。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [[5，6，3]，[8，6，2]，[2，5，1]]
> **输出** : [(5，6)，(6，3)，(8，6)，(6，2)，(2，5)，(5，1)]
> 
> **输入** : test_list = [[5，6，3]]
> **输出** : [(5，6)，(6，3)]

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们迭代每个列表，提取连续的元素，并将它们作为对添加到结果列表中。

```
# Python3 code to demonstrate working of 
# Convert Matrix to overlapping Tuple Pairs
# Using loop

# initializing list
test_list = [[5, 6, 7], [8, 6, 5], [2, 5, 7]]

# printing original list
print("The original list is : " + str(test_list))

# Convert Matrix to overlapping Tuple Pairs
# Using loop
res = []
for sub in test_list:
  res.append((sub[0], sub[1]))
  res.append((sub[1], sub[2]))

# printing result 
print("Filtered tuples : " + str(res)) 
```

**Output :**

```
The original list is : [[5, 6, 7], [8, 6, 5], [2, 5, 7]]
Filtered tuples : [(5, 6), (6, 7), (8, 6), (6, 5), (2, 5), (5, 7)]

```

**方法 2:使用循环+列表切片**
以上功能的组合可以用来解决这个问题。这提供了将逻辑扩展到更多定制元组大小(也超过 2)的灵活性。

```
# Python3 code to demonstrate working of 
# Convert Matrix to overlapping Tuple Pairs
# Using loop + list slicing

# initializing list
test_list = [[5, 6, 7], [8, 6, 5], [2, 5, 7]]

# printing original list
print("The original list is : " + str(test_list))

# Convert Matrix to overlapping Tuple Pairs
# Using loop + list slicing
res = []
for sub in test_list:
    for idx in range(len(sub) -1):
        res.append(tuple(sub[idx:idx + 2]))

# printing result 
print("Filtered tuples : " + str(res)) 
```

**Output :**

```
The original list is : [[5, 6, 7], [8, 6, 5], [2, 5, 7]]
Filtered tuples : [(5, 6), (6, 7), (8, 6), (6, 5), (2, 5), (5, 7)]

```