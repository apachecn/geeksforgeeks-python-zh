# Python |转换为 N*N 元组矩阵

> 原文:[https://www . geesforgeks . org/python-conversion-to-nn-tuple-matrix/](https://www.geeksforgeeks.org/python-conversion-to-nn-tuple-matrix/)

有时，在处理数据时，我们会遇到这样一个问题，即我们以元组矩阵的形式拥有长度不均匀的行。在这种情况下，需要用默认值完成 N*N 矩阵。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用 loop + `* operator`**
这个问题可以使用 loop 解决。这是执行这个任务的蛮力方法。我们只是追加默认值的次数，因为数据在一行中比 n 少

```
# Python3 code to demonstrate working of
# Conversion to N * N tuple matrix 
# using loop + * operator

# initialize tuple
test_tup = ((5, 4), (3, ), (1, 5, 6, 7), (2, 4, 5))

# printing original tuple
print("The original tuple is : " + str(test_tup))

# initializing dimension
N = 4

# Conversion to N * N tuple matrix 
# using loop + * operator
res = []
for tup in test_tup :
    res.append( tup +(0, ) * (N - len(tup)))

# printing result
print("Tuple after filling values : " + str(res))
```

**Output :**

```
The original tuple is : ((5, 4), (3, ), (1, 5, 6, 7), (2, 4, 5))
Tuple after filling values : [(5, 4, 0, 0), (3, 0, 0, 0), (1, 5, 6, 7), (2, 4, 5, 0)]

```