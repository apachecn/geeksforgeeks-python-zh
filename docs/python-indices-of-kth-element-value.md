# Python | Kth 元素值的索引

> 原文:[https://www . geeksforgeeks . org/python-indexs-of-kth-element-value/](https://www.geeksforgeeks.org/python-indices-of-kth-element-value/)

有时，在处理记录时，我们可能会遇到一个问题，即我们需要在元组的特定 Kth 位置找到特定值的所有元素索引。这似乎是一个特殊的问题，但是在处理记录中的许多键时，我们会遇到这个问题。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环**

这是解决这个问题的强力方法。在这种情况下，我们为索引保留一个计数器，如果我们在元组中的第 Kth 个位置找到特定的记录，就追加到列表中。

```py
# Python3 code to demonstrate working of
# Indices of Kth element value
# Using loop

# initialize list 
test_list = [(3, 1, 5), (1, 3, 6), (2, 5, 7),
                        (5, 2, 8), (6, 3, 0)]

# printing original list
print("The original list is : " + str(test_list))

# initialize ele 
ele = 3

# initialize K 
K = 1 

# Indices of Kth element value
# Using loop
# using y for K = 1 
res = []
count = 0
for x, y, z in test_list:
    if y == ele:
        res.append(count)
    count = count + 1

# printing result
print("The indices of element at Kth position : " + str(res))
```

**Output :**

> 原列表为:[(3，1，5)，(1，3，6)，(2，5，7)，(5，2，8)，(6，3，0)]
> 第 k 个位置元素的索引:[1，4]

**方法二:使用`enumerate()` +列表理解**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用`enumerate()`来列举索引，其余的按照上述方法执行，但是以紧凑的方式。

```py
# Python3 code to demonstrate working of
# Indices of Kth element value
# Using enumerate() + list comprehension

# initialize list 
test_list = [(3, 1, 5), (1, 3, 6), (2, 5, 7), 
                        (5, 2, 8), (6, 3, 0)]

# printing original list
print("The original list is : " + str(test_list))

# initialize ele 
ele = 3

# initialize K 
K = 1 

# Indices of Kth element value
# Using enumerate() + list comprehension
res = [a for a, b in enumerate(test_list) if b[K] == ele]

# printing result
print("The indices of element at Kth position : " + str(res))
```

**Output :**

> 原列表为:[(3，1，5)，(1，3，6)，(2，5，7)，(5，2，8)，(6，3，0)]
> 第 k 个位置元素的索引:[1，4]