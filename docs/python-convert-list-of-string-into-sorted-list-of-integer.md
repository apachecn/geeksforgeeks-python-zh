# Python |将字符串列表转换为整数排序列表

> 原文:[https://www . geesforgeks . org/python-convert-list-of-string-to-sorted-list-of-integer/](https://www.geeksforgeeks.org/python-convert-list-of-string-into-sorted-list-of-integer/)

给定一个字符串列表，编写一个 Python 程序将其转换为整数排序列表。

**示例:**

```
Input: ['21', '1', '131', '12', '15']
Output: [1, 12, 15, 21, 131]

Input: ['11', '1', '58', '15', '0']
Output: [0, 1, 11, 15, 58]

```

我们来讨论一下可以实现这个任务的不同方法。

**方法 1:** 使用`map` 和`sorted()`

```
# Python code to convert list of
# string into sorted list of integer

# List initialization
list_string = ['21', '1', '131', '12', '15']

# mapping
list_map = map(int, list_string)

# sorting list
list_sorted = sorted(list_map)

# Printing sorted list of integers
print(list_sorted)
```

**Output:**

```
[1, 12, 15, 21, 131]

```

**方法 2:** 使用列表理解

```
# Python code to convert list of 
# string into sorted list of integer

# List initialization
list_string = ['11', '1', '58', '15', '0']

# Using list comprehension
output = [int(x) for x in list_string]

# using sort function
output.sort()

# Printing output
print(output)
```

**Output:**

```
[0, 1, 11, 15, 58]

```

**方法#3:** 使用迭代

```
# Python code to convert list of
# string into sorted list of integer

# List initialization
list_string = ['11', '1', '58', '15', '0']

# using iteration and sorted()
list_sorted = sorted(int(x) for x in list_string)

# printing output
print(list_sorted)
```

**Output:**

```
[0, 1, 11, 15, 58]

```