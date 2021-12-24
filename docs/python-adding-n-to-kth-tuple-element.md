# Python |向第 k 个元组元素添加 N

> 原文:[https://www . geesforgeks . org/python-add-n-to-kth-tuple-element/](https://www.geeksforgeeks.org/python-adding-n-to-kth-tuple-element/)

很多时候，在处理记录时，我们会遇到一个问题，那就是我们需要更改元组元素的值。这是使用元组时常见的问题。让我们讨论一些方法，可以将 N 添加到列表中元组的第 Kth 个元素中。

**方法#1:使用循环**
使用循环可以执行该任务。在这种情况下，我们只需迭代列表，通过代码中的预定义值 N 来更改 Kth 元素。

```py
# Python3 code to demonstrate working of
# Adding N to Kth tuple element
# Using loop

# Initializing list
test_list = [(4, 5, 6), (7, 4, 2), (9, 10, 11)]

# printing original list
print("The original list is : " + str(test_list))

# Initializing N 
N = 3 

# Initializing K 
K = 1

# Adding N to Kth tuple element
# Using loop
res = []
for i in range(0, len(test_list)):
    res.append((test_list[i][0], test_list[i][K] + N, test_list[i][2]))

# printing result
print("The tuple after adding N to Kth element : " + str(res))
```

**Output :**

```py
The original list is : [(4, 5, 6), (7, 4, 2), (9, 10, 11)]
The tuple after adding N to Kth element : [(4, 8, 6), (7, 7, 2), (9, 13, 11)]

```