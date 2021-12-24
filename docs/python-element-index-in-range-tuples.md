# Python–范围元组中的元素索引

> 原文:[https://www . geesforgeks . org/python-元素-范围内索引-元组/](https://www.geeksforgeeks.org/python-element-index-in-range-tuples/)

有时，在处理 Python 数据时，我们可能会遇到一个问题，即我们需要在列表中的连续等范围元组中找到元素位置。这个问题在许多领域都有应用，包括日常编程和竞争性编程。让我们讨论执行这项任务的某些方法。

> **输入** :
> 测试 _ 列表= [(0，10)，(11，20)，(21，30)，(31，40)]
> K = 37
> T5】输出:3
> T8】输入 :
> 测试 _ 列表= [(0，9)，(10，19)，(20，29)，(30，39)]
> K = 37
> **输出**:3【T11

**方法#1:使用循环**
这是可以执行该任务的蛮力方式。在这种情况下，我们迭代列表中的所有元素，然后使用比较运算符，找到所需元素的位置。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Element Index in Range Tuples
# Using loop

# initializing list
test_list = [(0, 10), (11, 20), (21, 30), (31, 40), (41, 50)]

# printing original list
print("The original list is : " + str(test_list))

# initializing Element
K = 37

# Element Index in Range Tuples
# Using loop
res = None
for idx, ele in enumerate(test_list):
    if K >= ele[0] and K <= ele[1]:
        res = idx

# printing result
print("The position of element : " + str(res))
```

**Output : **

```py
The original list is : [(0, 10), (11, 20), (21, 30), (31, 40), (41, 50)]
The position of element : 3
```

**方法 2:使用公式**
元素位置也可以不使用循环进行划分，而是使用范围大小的元素划分进行提取，保持一致。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Element Index in Range Tuples
# Using formula

# initializing list
test_list = [(0, 10), (11, 20), (21, 30), (31, 40), (41, 50)]

# printing original list
print("The original list is : " + str(test_list))

# initializing Element
K = 37

# Element Index in Range Tuples
# Using formula
res = (K // (test_list[0][1] - test_list[0][0]))

# printing result
print("The position of element : " + str(res))
```

**Output : **

```py
The original list is : [(0, 10), (11, 20), (21, 30), (31, 40), (41, 50)]
The position of element : 3
```