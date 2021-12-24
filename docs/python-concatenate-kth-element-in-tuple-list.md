# Python–连接元组列表中的第 Kth 个元素

> 原文:[https://www . geesforgeks . org/python-concatenate-kth-tuple 中的元素列表/](https://www.geeksforgeeks.org/python-concatenate-kth-element-in-tuple-list/)

在使用元组时，我们将不同的数据存储为不同的元组元素。有时，需要打印元组中的特定信息。例如，一段代码希望所有学生数据的名字都以串联格式打印出来。让我们讨论一下如何解决这个问题。

**方法一:使用列表理解+ join()**
列表理解是解决这个问题最简单的方法。我们可以只迭代所有索引中的特定索引值，并将其存储在列表中，然后使用 join()连接它。

```py
# Python3 code to demonstrate 
# Concatenating Kth element in Tuple List
# using list comprehension 

# initializing list of tuples
test_list = [(1, 'Rash', 21), (2, 'Varsha', 20), (3, 'Kil', 19)]

# printing original list 
print ("The original list is : " + str(test_list))

# initializing K 
K = 1

# using list comprehension + join() to concatenate names
res = " ".join([lis[K] for lis in test_list])

# printing result
print ("String with only Kth tuple element (i.e names) concatenated : " + str(res))
```

**Output :**

```py
The original list is : [(1, 'Rash', 21), (2, 'Varsha', 20), (3, 'Kil', 19)]
String with only Kth tuple element (i.e names) concatenated : Rash Varsha Kil

```