# Python–列表中的索引值重复

> 原文:[https://www . geesforgeks . org/python-index-value-repeat-in-list/](https://www.geeksforgeeks.org/python-index-value-repetition-in-list/)

给定一个元素列表，任务是编写一个 Python 程序来根据索引中的值重复每个索引值。

> **输入**:test _ list =【3，0，4，2】
> **输出**:【0，0，0，2，2，2，2，3，3】
> **解释** : 0 重复 3 次，因为其索引值为 3。
> 
> **输入**:test _ list =【3，4，2】
> **输出**:【0，0，0，1，1，1，1，1，2】
> **解释** : 1 重复 4 次，因为其值为 4。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/)

在这种情况下，我们使用*运算符执行重复任务，并使用 enumerate()获取索引和重复值。列表理解用于迭代所有元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Index Value repetition in List
# Using list comprehension + enumerate()

# initializing Matrix
test_list = [3, 0, 4, 2]

# printing original list
print("The original list is : " + str(test_list))

# enumerate() gets index and value of similar index element
res = [ele for sub in ([idx] * ele for idx, 
                       ele in enumerate(test_list)) for ele in sub]

# printing result
print("Constructed List : " + str(res))
```

**输出:**

```
The original list is : [3, 0, 4, 2]
Constructed List : [0, 0, 0, 2, 2, 2, 2, 3, 3]
```

**方法 2:使用** [**链. from _ iterable()**](https://www.geeksforgeeks.org/python-itertools-chain-from_iterable/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在本文中，我们使用 chain.from_iterable()执行列表展平的最后一步。列表理解执行所有元素的迭代任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Index Value repetition in List
# Using chain.from_iterable() + list comprehension
import itertools

# initializing Matrix
test_list = [3, 0, 4, 2]

# printing original list
print("The original list is : " + str(test_list))

# enumerate() gets index and
# value of similar index element
# from_iterable() used to flatten
res = list(itertools.chain(*([idx] * ele for idx, 
                             ele in enumerate(test_list))))

# printing result
print("Constructed List : " + str(res))
```

**输出:**

```
The original list is : [3, 0, 4, 2]
Constructed List : [0, 0, 0, 2, 2, 2, 2, 3, 3]
```