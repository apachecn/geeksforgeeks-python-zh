# Python–将列表列表转换为集合列表

> 原文:[https://www . geesforgeks . org/python-convert-list-list-to-list-set/](https://www.geeksforgeeks.org/python-convert-list-of-lists-to-list-of-sets/)

给定一个包含列表的列表，任务是编写一个 Python 程序，将其转换为包含集合的列表。

**示例:**

```py
Input : [[1, 2, 1], [1, 2, 3], [2, 2, 2, 2], [0]]
Output : [{1, 2}, {1, 2, 3}, {2}, {0}]

Input : [[4, 4], [5, 5, 5], [1, 2, 3]]
Output : [{4}, {5}, {1, 2, 3}]
```

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

使用列表理解很容易做到这一点。我们只是遍历每个列表，将列表转换成集合。

## 蟒蛇 3

```py
# python3 program to convert list
# of lists to a list of sets

# initializing list
test_list = [[1, 2, 1], [1, 2, 3], [2, 2, 2, 2], [0]]

# printing original list
print("The original list of lists : " + str(test_list))

# using list comprehension
# convert list of lists to list of sets
res = [set(ele) for ele in test_list]

# print result
print("The converted list of sets : " + str(res))
```

**输出:**

```py
he original list of lists : [[1, 2, 1], [1, 2, 3], [2, 2, 2, 2], [0]]
The converted list of sets : [{1, 2}, {1, 2, 3}, {2}, {0}]
```

**方法二:使用** [**地图()**](https://www.geeksforgeeks.org/python-map-function/) **+** [**设置**](https://www.geeksforgeeks.org/python-sets/)

我们可以使用 map 函数和 set 运算符的组合来执行这个特定的任务。map 函数绑定每个列表，并将其转换为集合。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# convert list of lists to list of sets
# using map() + set

# initializing list
test_list = [[1, 2, 1], [1, 2, 3], [2, 2, 2, 2], [0]]

# printing original list
print("The original list of lists : " + str(test_list))

# using map() + set
res = list(map(set, test_list))

# print result
print("The converted list of sets : " + str(res))
```

**输出:**

```py
The original list of lists : [[1, 2, 1], [1, 2, 3], [2, 2, 2, 2], [0]]
The converted list of sets : [{1, 2}, {1, 2, 3}, {2}, {0}]
```