# Python–将列表转换为元组中的单值列表

> 原文:[https://www . geesforgeks . org/python-convert-list-to-single-value-list-in-tuple/](https://www.geeksforgeeks.org/python-convert-list-to-single-valued-lists-in-tuple/)

数据类型的转换是目前 CS 域中最常见的问题。一个这样的问题可能是将列表元素转换为元组中的单值列表。这可以在数据预处理领域得到应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [1，3，5，6，7，9]
> **输出** : ([1]，[3]，[5]，[6]，[7]，[9])
> 
> **输入** : test_list = [1]
> **输出** : ([1])

**方法#1:使用列表理解+元组()**
这是可以执行此任务的方法之一。在本文中，我们使用列表理解构造并迭代列表，最后使用 tuple()将结果列表转换为 tuple。

```
# Python3 code to demonstrate working of 
# Convert List to Single valued Lists in Tuple
# Using list comprehension + tuple()

# initializing lists
test_list = [6, 8, 4, 9, 10, 2]

# printing original list
print("The original list is : " + str(test_list))

# Convert List to Single valued Lists in Tuple
# Using list comprehension + tuple()
res = tuple([ele] for ele in test_list)

# printing result 
print("Tuple after conversion : " + str(res)) 
```

**Output :**

```
The original list is : [6, 8, 4, 9, 10, 2]
Tuple after conversion : ([6], [8], [4], [9], [10], [2])

```

**方法 2:使用`map() + list() + zip() + tuple()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 map()执行将转换逻辑扩展到每个元素的任务，并使用 zip()列出到每个元素的转换。最后，使用 tuple()将结果转换回 tuple。

```
# Python3 code to demonstrate working of 
# Convert List to Single valued Lists in Tuple
# Using map() + list() + zip() + tuple()

# initializing lists
test_list = [6, 8, 4, 9, 10, 2]

# printing original list
print("The original list is : " + str(test_list))

# Convert List to Single valued Lists in Tuple
# Using map() + list() + zip() + tuple()
res = tuple(map(list, zip(test_list)))

# printing result 
print("Tuple after conversion : " + str(res)) 
```

**Output :**

```
The original list is : [6, 8, 4, 9, 10, 2]
Tuple after conversion : ([6], [8], [4], [9], [10], [2])

```