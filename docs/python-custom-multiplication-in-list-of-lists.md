# Python |列表列表中的自定义乘法

> 原文:[https://www . geesforgeks . org/python-列表中自定义乘法/](https://www.geeksforgeeks.org/python-custom-multiplication-in-list-of-lists/)

有时，当我们收到列表的列表时，我们需要将它的每个元素列表与另一个列表中的顺序所提供的特定元素相乘。这个特殊的问题非常具体，但在这种情况下，对它的了解会很有用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用循环**

这是执行这个特殊任务的天真而暴力的方法，在这个任务中，我们运行一个循环来获取所有元素及其嵌套组件，并相应地进行乘法运算。

```py
# Python3 code to demonstrate
# Custom Multiplication in list of lists
# Using loops

# initializing list
test_list = [[5, 6, 8], [7, 4, 3], [8, 10, 12]]

# initializing multiply list 
mult_list = [10, 20, 30]

# printing original list
print("The original list : " + str(test_list))

# printing multiply list
print("The original multiply list : " + str(mult_list))

# using loops
# Custom Multiplication in list of lists
res = [[] for idx in range(len(test_list))]
for i in range(len(test_list)):
    for j in range(len(mult_list)):
        res[i] += [mult_list[i] * test_list[i][j]]

# print result
print("The list after multiply : " + str(res))
```

**Output :**

```py
The original list : [[5, 6, 8], [7, 4, 3], [8, 10, 12]]
The original multiply list : [10, 20, 30]
The list after multiply : [[50, 60, 80], [140, 80, 60], [240, 300, 360]]

```

**方法 2:使用列表理解+ `enumerate()`**

这个问题也可以用更短的方法解决，利用`enumerate` 函数的幂一次得到容器的指数和值。这是解决这个问题的一种方法。

```py
# Python3 code to demonstrate
# Custom Multiplication in list of lists
# Using list comprehension + enumerate()

# initializing list
test_list = [[5, 6, 8], [7, 4, 3], [8, 10, 12]]

# initializing multiply list 
mult_list = [10, 20, 30]

# printing original list
print("The original list : " + str(test_list))

# printing multiply list
print("The original multiply list : " + str(mult_list))

# using list comprehension + enumerate()
# Custom Multiplication in list of lists
res = [[mult_list[i] * j for j in sub] 
       for i, sub in enumerate(test_list)]

# print result
print("The list after multiply : " + str(res))
```

**Output :**

```py
The original list : [[5, 6, 8], [7, 4, 3], [8, 10, 12]]
The original multiply list : [10, 20, 30]
The list after multiply : [[50, 60, 80], [140, 80, 60], [240, 300, 360]]

```