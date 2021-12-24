# Python–字典位置等于键或值时计数

> 原文:[https://www . geesforgeks . org/python-count-if-dictionary-position-equal-key-or-value/](https://www.geeksforgeeks.org/python-count-if-dictionary-position-equals-key-or-value/)

给定一个字典，统计字典项目位置等于键或值的实例。适用于 Py >= 3.6 [字典排序介绍]。

> **输入** : test_dict = {5:3，2:3，10:4，7:3，8:1，9:5}
> **输出** : 2
> **解释**:在 3、5 位，数值为 3、5。
> 
> **输入** : test_dict = {5:3，2:3，10:4，8:1，9:5}
> **输出** : 1
> **说明**:第 5 位，数值为 5。

**方法#1:使用循环**

在这种情况下，我们对每个字典项目进行迭代，并对每个项目进行测试，以检查是否有任何位置等于字典的键或值，如果找到，我们就迭代计数器。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Count if dictionary position equals key or value
# Using loop

# initializing dictionary
test_dict = {5: 3, 1: 3, 10: 4, 7: 3, 8: 1, 9: 5}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

res = 0
test_dict = list(test_dict.items())
for idx in range(0, len(test_dict)):

    # checking for key or value equality
    if idx == test_dict[idx][0] or idx == test_dict[idx][1]:
        res += 1

# printing result
print("The required frequency : " + str(res))
```

**Output**

```py
The original dictionary is : {5: 3, 1: 3, 10: 4, 7: 3, 8: 1, 9: 5}
The required frequency : 3

```

**方法 2:使用** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们为每个字典索引等于它的任何项目的情况分配 1，然后使用 sum()执行列表求和。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Count if dictionary position equals key or value
# Using sum() + list comprehension

# initializing dictionary
test_dict = {5: 3, 1: 3, 10: 4, 7: 3, 8: 1, 9: 5}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

test_dict = list(test_dict.items())

# sum() computing sum for filtered cases
res = sum([1 for idx in range(0, len(test_dict)) if idx ==
           test_dict[idx][0] or idx == test_dict[idx][1]])

# printing result
print("The required frequency : " + str(res))
```

**Output**

```py
The original dictionary is : {5: 3, 1: 3, 10: 4, 7: 3, 8: 1, 9: 5}
The required frequency : 3

```