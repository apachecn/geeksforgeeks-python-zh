# Python |将常量划分为第 k 个元组索引

> 原文:[https://www . geesforgeks . org/python-divide-常量到 kth-tuple-index/](https://www.geeksforgeeks.org/python-divide-constant-to-kth-tuple-index/)

很多时候，在处理记录时，我们会遇到一个问题，那就是我们需要更改元组元素的值。这是使用元组时常见的问题。让我们讨论用列表中元组的 Kth 元素划分 N 的某些方法。

**方法#1:使用循环**
使用循环可以执行该任务。在这种情况下，我们只需迭代列表，通过代码中的预定义值 N 来更改 Kth 元素。

```py
# Python3 code to demonstrate working of
# Divide constant to Kth Tuple index
# Using loop

# Initializing list
test_list = [(4, 5, 6), (7, 4, 2), (9, 10, 11)]

# printing original list
print("The original list is : " + str(test_list))

# Initializing N 
N = 3

# Initializing K 
K = 1

# Divide constant to Kth Tuple index
# Using loop
res = []
for i in range(0, len(test_list)):
    res.append((test_list[i][0], test_list[i][K] // N, test_list[i][2]))

# printing result
print("The tuple after dividing N to Kth element : " + str(res))
```

**Output :**

```py
The original list is : [(4, 5, 6), (7, 4, 2), (9, 10, 11)]
The tuple after dividing N to Kth element : [(4, 1, 6), (7, 1, 2), (9, 3, 11)]

```