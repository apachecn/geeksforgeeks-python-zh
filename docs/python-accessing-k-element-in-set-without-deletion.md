# Python–不删除访问集合中的 K 元素

> 原文:[https://www . geesforgeks . org/python-access-k-element-in-set-not-delete/](https://www.geeksforgeeks.org/python-accessing-k-element-in-set-without-deletion/)

在本文中，给定一个集合()，任务是编写一个 Python 程序来访问元素 K，而不使用 pop()执行删除。

**示例:**

```py
Input : test_set = {6, 4, 2, 7, 9}, K = 7
Output : 3
Explanation : 7 occurs in 3rd index in set.

Input : test_set = {6, 4, 2, 7, 9}, K = 9
Output : 4
Explanation : 9 occurs in 4th index in set.
```

**方法#1:使用循环**

最通用的方法是使用循环执行迭代，如果找到 K，打印元素，如果需要，打印索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Accessing K element in set without deletion
# Using loop

# initializing set
test_set = {6, 4, 2, 7, 9}

# printing original set
print("The original set is : " + str(test_set))

# initializing K
K = 7

res = -1
for ele in test_set:

    # checking for K element
    res += 1
    if ele == K:
        break

# printing result
print("Position of K in set : " + str(res))
```

**输出:**

```py
The original set is : {2, 4, 6, 7, 9}
Position of K in set : 3
```

**方法 2:使用**[**next()**](https://www.geeksforgeeks.org/python-next-method/)**+**[**ITER()**](https://www.geeksforgeeks.org/python-iter-method/)

在这种情况下，容器被转换为迭代器，next()用于增加位置指针，当找到元素时，我们从循环中断开。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Accessing K element in set without deletion
# Using next() + iter()

# initializing set
test_set = {6, 4, 2, 7, 9}

# printing original set
print("The original set is : " + str(test_set))

# initializing K
K = 7

set_iter = iter(test_set)
for idx in range(len(test_set)):

    # incrementing position
    ele = next(set_iter)
    if ele == K:
        break

# printing result
print("Position of K in set : " + str(idx))
```

**输出:**

```py
The original set is : {2, 4, 6, 7, 9}
Position of K in set : 3
```