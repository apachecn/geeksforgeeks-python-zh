# Python–连续元组差异

> 原文:[https://www . geesforgeks . org/python-continuous-tuple-difference/](https://www.geeksforgeeks.org/python-consecutive-tuple-difference/)

给定元组列表，找到连续元组的索引绝对差。

> **输入** : test_list = [(5，3)，(1，4)，(9，5)，(3，5)]
> **输出** : [(4，1)，(7，1)，(6，0)]
> **解释**:5–1 = 4，4–3 = 1。因此是(4，1)等等。
> 
> **输入** : test_list = [(9，5)，(3，5)]
> **输出** : [(6，0)]
> **解释**:9–3 = 6，5–5 = 0。

**方法一:使用列表理解**

这是执行这项任务的一种方式。在这种情况下，我们使用蛮力策略对列表使用列表理解策略来执行这个任务作为一个线性。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Consecutive Tuple difference
# Using list comprehension

# initializing lists
test_list = [(6, 3), (1, 4), (8, 5), (3, 5)]

# printing original list
print("The original list : " + str(test_list))

# using list comprehension to perform absolute difference
# using abs() for difference
res = [(abs(test_list[idx + 1][0] - test_list[idx][0]), abs(test_list[idx + 1][1] - test_list[idx][1])) 
      for idx in range(len(test_list) - 1)]

# printing result 
print("The extracted list : " + str(res))
```

**Output**

```
The original list : [(6, 3), (1, 4), (8, 5), (3, 5)]
The extracted list : [(5, 1), (7, 1), (5, 0)]

```

**方法 2:使用元组()+ map() + sub**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 sub 执行减法的任务，map()用于将逻辑扩展到整个列表元素。不输出绝对结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Consecutive Tuple difference
# Using tuple() + map() + sub
from operator import sub

# initializing lists
test_list = [(6, 3), (1, 4), (8, 5), (3, 5)]

# printing original list
print("The original list : " + str(test_list))

# using loop to iterate elements
# using sub and map() to perform the subtraction to whole elements
res = []
for idx in range(len(test_list) - 1):
    res.append(tuple(map(sub, test_list[idx + 1][0:], test_list[idx][0:])))

# printing result 
print("The extracted list : " + str(res))
```

**Output**

```
The original list : [(6, 3), (1, 4), (8, 5), (3, 5)]
The extracted list : [(-5, 1), (7, 1), (-5, 0)]

```