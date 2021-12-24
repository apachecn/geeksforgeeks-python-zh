# Python–第 n 列常数乘法

> 原文:[https://www . geesforgeks . org/python-常量-乘法-to-n-column/](https://www.geeksforgeeks.org/python-constant-multiplication-to-nth-column/)

很多时候，在处理记录时，我们会遇到一个问题，那就是我们需要更改元组元素的值。这是使用元组时常见的问题。让我们讨论 K 可以乘以列表中元组的第 n 个元素的某些方法。

**方法#1:使用循环**
使用循环可以执行该任务。在这种情况下，我们只需迭代列表，通过代码中的预定义值 K 来更改第 n 个元素。

```py
# Python3 code to demonstrate working of
# Constant Multiplication to Nth Column
# Using loop

# Initializing list
test_list = [(4, 5, 6), (7, 4, 2), (9, 10, 11)]

# printing original list
print("The original list is : " + str(test_list))

# Initializing N 
N = 1

# Initializing K 
K = 3

# Constant Multiplication to Nth Column
# Using loop
res = []
for i in range(0, len(test_list)):
    res.append((test_list[i][0], test_list[i][N] * K, test_list[i][2]))

# printing result
print("The tuple after multiplying K to Nth element : " + str(res))
```

**Output :**

```py
The original list is : [(4, 5, 6), (7, 4, 2), (9, 10, 11)]
The tuple after multiplying K to Nth element : [(4, 15, 6), (7, 12, 2), (9, 30, 11)]

```