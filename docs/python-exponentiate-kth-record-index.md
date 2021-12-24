# Python |指数化第 Kth 条记录索引

> 原文:[https://www . geeksforgeeks . org/python-exp 指数-kth-record-index/](https://www.geeksforgeeks.org/python-exponentiate-kth-record-index/)

很多时候，在处理记录时，我们会遇到一个问题，那就是我们需要更改元组元素的值。这是使用元组时常见的问题。让我们讨论 N 可以指数化为列表中元组的第 Kth 个元素的某些方法。

**方法#1:使用循环**
使用循环可以执行该任务。在这种情况下，我们只需迭代列表，通过代码中的预定义值 N 来更改 Kth 元素。

```py
# Python3 code to demonstrate working of
# Exponentiate Kth Record Index
# Using loop

# Initializing list
test_list = [(4, 5, 6), (7, 4, 2), (9, 10, 11)]

# printing original list
print("The original list is : " + str(test_list))

# Initializing N 
N = 3

# Initializing K 
K = 1

# Exponentiate Kth Record Index
# Using loop
res = []
for i in range(0, len(test_list)):
    res.append((test_list[i][0], test_list[i][K] ** N, test_list[i][2]))

# printing result
print("The tuple after Exponentiating N to Kth element : " + str(res))
```

**Output :**

```py
The original list is : [(4, 5, 6), (7, 4, 2), (9, 10, 11)]
The tuple after Exponentiating N to Kth element : [(4, 125, 6), (7, 64, 2), (9, 1000, 11)]

```