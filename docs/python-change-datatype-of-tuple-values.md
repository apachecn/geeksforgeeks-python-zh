# Python–更改元组值的数据类型

> 原文:[https://www . geesforgeks . org/python-change-datatype-of-tuple-values/](https://www.geeksforgeeks.org/python-change-datatype-of-tuple-values/)

有时，在处理记录集时，我们可能会遇到这样的问题，即需要对元组的值进行数据类型更改，元组位于其第二个位置，即值位置。这种问题可能发生在包括数据操作的所有领域。让我们讨论执行这项任务的某些方法。

```
Input : test_list = [(44, 5.6), (16, 10)]
Output : [(44, '5.6'), (16, '10')]

Input : test_list = [(44, 5.8)]
Output : [(44, '5.8')]

```

**方法#1:使用`enumerate()` +循环**
这是解决这个问题的蛮力方式。在这种情况下，我们通过使用适当的数据类型转换函数将元组所需的索引更改为类型转换来重新分配元组值。

```
# Python3 code to demonstrate working of 
# Change Datatype of Tuple Values
# Using enumerate() + loop

# initializing list
test_list = [(4, 5), (6, 7), (1, 4), (8, 10)]

# printing original list
print("The original list is : " + str(test_list))

# Change Datatype of Tuple Values
# Using enumerate() + loop
# converting to string using str()
for idx, (x, y) in enumerate(test_list):
    test_list[idx] = (x, str(y))

# printing result 
print("The converted records : " + str(test_list)) 
```

**Output :**

```
The original list is : [(4, 5), (6, 7), (1, 4), (8, 10)]
The converted records : [(4, '5'), (6, '7'), (1, '4'), (8, '10')]

```