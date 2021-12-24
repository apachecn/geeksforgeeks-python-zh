# Python–大于 K 的位数平均值

> 原文:[https://www . geesforgeks . org/python-大于 k 的位数平均值/](https://www.geeksforgeeks.org/python-average-of-digit-greater-than-k/)

给定元素列表，提取位数平均值大于 k 的元素

> **输入**:test _ list =【633，719，8382，119，327】，K = 5
> **输出**:【719，8382】
> **解释** : (7 + 1 + 9) / 3 = 5.6 和(8 + 3 + 8 + 2) / 4 = 5.2，均大于 5，因此返回。
> 
> **输入**:test _ list =【633，719，8382，96】，K = 5
> **输出**:【719，8382，96】
> **说明:**数字平均值大于 5 的输出显示所有元素。

**方法一:使用列表理解+ sum() + len()**

在这种情况下，我们使用 *sum()* 计算数字总和，然后将总和除以元素长度得到平均值，如果大于 k，则加入结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Average digit greater than K
# Using sum() + len() + list comprehension

# initializing list
test_list = [633, 719, 8382, 119, 327]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

# getting average and checking if greater than K
res = [sub for sub in test_list if sum(
    [int(ele) for ele in str(sub)]) / len(str(sub)) >= K]

# printing result
print("Filtered List : " + str(res))
```

**输出:**

```
The original list is : [633, 719, 8382, 119, 327]
Filtered List : [719, 8382]

```

**方法 2:使用 sum() + len() + filter() + lambda**

这里，使用*滤波器()*和*λ*进行滤波操作，其余所有操作都按照上述方法处理。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Average digit greater than K
# Using sum() + len() + filter() + lambda

# initializing list
test_list = [633, 719, 8382, 119, 327]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

# getting average and checking if greater than K
# using filter() and lambda to filter
res = list(filter(lambda sub: sum(
    [int(ele) for ele in str(sub)]) / len(str(sub)) >= K, test_list))

# printing result
print("Filtered List : " + str(res))
```

**输出:**

```
The original list is : [633, 719, 8382, 119, 327]
Filtered List : [719, 8382]

```