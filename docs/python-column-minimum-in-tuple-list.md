# Python–元组列表中的最小列数

> 原文:[https://www . geesforgeks . org/python-column-in-minimum-tuple-list/](https://www.geeksforgeeks.org/python-column-minimum-in-tuple-list/)

有时，在处理记录时，我们会遇到一个问题，即我们需要找到元组列表容器中所有列的最小值。这种应用在 web 开发领域很常见。让我们讨论执行这项任务的某些方法。
**方法#1:使用 min() +列表理解+ zip()**
该任务可以使用上述功能的组合来执行。在本文中，我们使用 zip()对相似的索引元素(即列)进行模拟，然后使用列表理解对它们进行迭代，并使用 min()执行最小化。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Column Minimum in Tuple list
# using list comprehension + min() + zip()

# initialize list
test_list = [(1, 2, 3), (6, 7, 6), (1, 6, 8)]

# printing original list
print("The original list : " + str(test_list))

# Column Minimum in Tuple list
# using list comprehension + min() + zip()
res = [min(ele) for ele in zip(*test_list)]

# printing result
print("The Cumulative column minimum is : " + str(res))
```

**Output**

```py
The original list : [(1, 2, 3), (6, 7, 6), (1, 6, 8)]
The Cumulative column minimum is : [1, 2, 3]

```

**方法 2:使用 zip() + map() + min()**
此方法与上述方法类似。在这种情况下，由列表理解执行的任务由 map()执行，它将最少的列扩展到压缩的元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Column Minimum in Tuple list
# using zip() + map() + min()

# initialize list
test_list = [(1, 2, 3), (6, 7, 6), (1, 6, 8)]

# printing original list
print("The original list : " + str(test_list))

# Column Minimum in Tuple list
# using zip() + map() + min()
res = list(map(min, zip(*test_list)))

# printing result
print("The Cumulative column minimum is : " + str(res))
```

**Output**

```py
The original list : [(1, 2, 3), (6, 7, 6), (1, 6, 8)]
The Cumulative column minimum is : [1, 2, 3]

```