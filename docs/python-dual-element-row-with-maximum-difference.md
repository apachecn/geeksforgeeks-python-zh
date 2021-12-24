# Python–最大差异的双元素行

> 原文:[https://www . geesforgeks . org/python-双元素最大差异行/](https://www.geeksforgeeks.org/python-dual-element-row-with-maximum-difference/)

有时，在使用 Python Matrix 时，我们可以让 Matrix 的元素变成只有两个元素的行，并且我们可能希望得到具有最大差异的元素的行。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们对每一行进行迭代，计算最大值，并在每次迭代时存储差异较大的行。

```
# Python3 code to demonstrate 
# Dual Element row with Maximum difference
# using loop

# Initializing list
test_list = [[5, 10], [1, 3], [4, 11], [1, 2]]

# printing original list
print("The original list is : " + str(test_list))

# Dual Element row with Maximum difference
# using loop
max_till = -float('inf')
res = []
for sub in test_list:
    if abs(sub[0] - sub[1]) > max_till:
        max_till = abs(sub[0] - sub[1])
        res = sub

# printing result 
print ("The maximum difference row is : " + str(res))
```

**Output :**

```
The original list is : [[5, 10], [1, 3], [4, 11], [1, 2]]
The maximum difference row is : [4, 11]

```