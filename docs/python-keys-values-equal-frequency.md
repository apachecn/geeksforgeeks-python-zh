# Python–键值等频

> 原文:[https://www . geesforgeks . org/python-key-values-equal-frequency/](https://www.geeksforgeeks.org/python-keys-values-equal-frequency/)

给定一个字典，统计键等于值的实例。

> **输入** : test_dict = {5:5，8:9，7:8，1:2，10:10，4:8}
> **输出** : 2
> **解释**:在 2 个实例中，键等于值。
> 
> **输入** : test_dict = {5:4，8:9，7:8，1:2，10:10，4:8}
> **输出** : 1
> **解释**:在 1 个实例中，key 等于 value。

**方法#1:使用循环**

在这种情况下，我们计算键等于值的实例，并相应地增加计数器。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Keys Values equal frequency
# Using loop

# initializing dictionary
test_dict = {5: 5, 8: 9, 7: 7, 1: 2, 10: 10, 4: 8}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

res = 0
for key in test_dict:

    # checking for equality and incrementing counter
    if key == test_dict[key]:
        res += 1

# printing result
print("The required frequency : " + str(res))
```

**Output**

```py
The original dictionary is : {5: 5, 8: 9, 7: 7, 1: 2, 10: 10, 4: 8}
The required frequency : 3

```

**方法 2:使用** [**求和()**](https://www.geeksforgeeks.org/accumulate-and-partial_sum-in-c-stl-numeric-header/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，使用 sum()执行计数任务，当找到相等的键值时，将 1 追加到列表中，然后在末尾对每个值求和。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Keys Values equal frequency
# Using sum() + list comprehension

# initializing dictionary
test_dict = {5: 5, 8: 9, 7: 7, 1: 2, 10: 10, 4: 8}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# computing summation to get frequency
res = sum([1 for key in test_dict if key == test_dict[key]])

# printing result
print("The required frequency : " + str(res))
```

**Output**

```py
The original dictionary is : {5: 5, 8: 9, 7: 7, 1: 2, 10: 10, 4: 8}
The required frequency : 3

```