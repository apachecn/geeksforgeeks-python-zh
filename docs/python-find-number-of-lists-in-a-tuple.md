# Python |查找元组中的列表数量

> 原文:[https://www . geesforgeks . org/python-find-tuple 中的列表数/](https://www.geeksforgeeks.org/python-find-number-of-lists-in-a-tuple/)

给定一个列表元组，任务是找到一个元组中的列表数。这是一个非常基本的问题，但在进行一些实用应用时会很有用。

**方法#1:使用*镜头*T3】**

```
# Python code to find number of list in a tuple

# Initial list 
Input1 = ([1, 2, 3, 4], [5, 6, 7, 8])
Input2 = ([1, 2], [3, 4], [5, 6])
Input3 = ([9, 8, 7, 6, 5, 4, 3, 2, 1], [1, 2, 3])

# Using len to find no of list in tuple
Output1 = len(Input1)
Output2 = len(Input2)
Output3 = len(Input3)

# Printing
print("Initial list :")
print(Input1)
print("No of list in tuples are :")
print(Output1)
print("\n")

print("Initial list :")
print(Input2)
print("No of list in tuples are :")
print(Output2)
print("\n")

print("Initial list :")
print(Input3)
print("No of list in tuples are :")
print(Output3)
print("\n")
```

**Output:**

```
Initial list :
([1, 2, 3, 4], [5, 6, 7, 8])
No of list in tuples are :
2

Initial list :
([1, 2], [3, 4], [5, 6])
No of list in tuples are :
3

Initial list :
([9, 8, 7, 6, 5, 4, 3, 2, 1], [1, 2, 3])
No of list in tuples are :
2

```

**方法 2:使用功能和实例**

```
# Python code to find number of list in a tuple

# Using find function
def find(Input):
    if isinstance(Input, list):
        return 1
    else:
        return len(Input)

# List initialization
Input1 = ([1, 2, 3, 4], [5, 6, 7, 8])
Input2 = ([1, 2], [3, 4], [5, 6])
Input3 = ([9, 8, 7, 6, 5, 4, 3, 2, 1])

# using find
Output1 = find(Input1)
Output2 = find(Input2)
Output3 = find(Input3)

# printing
print("Initial list :")
print(Input1)
print("No of list in tuples are :")
print(Output1)
print("\n")

print("Initial list :")
print(Input2)
print("No of list in tuples are :")
print(Output2)
print("\n")

print("Initial list :")
print(Input3)
print("No of list in tuples are :")
print(Output3)
print("\n")
```

**Output:**

```
Initial list :
([1, 2, 3, 4], [5, 6, 7, 8])
No of list in tuples are :
2

Initial list :
([1, 2], [3, 4], [5, 6])
No of list in tuples are :
3

Initial list :
[9, 8, 7, 6, 5, 4, 3, 2, 1]
No of list in tuples are :
1

```