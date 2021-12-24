# Python–列表元素的增量和循环重复

> 原文:[https://www . geesforgeks . org/python-元素列表的增量和循环重复/](https://www.geeksforgeeks.org/python-incremental-and-cyclic-repetition-of-list-elements/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们需要将元素重复 K 次。但是我们可以在这方面有变化，必须以循环和增量的方式重复元素。让我们讨论执行这项任务的某些方法。
**方法#1:使用 loop + enumerate()**
这是可以执行这个任务的蛮力方式。在这种情况下，我们使用 mod 运算符和乘法逻辑迭代元素并执行所需的重复次数。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Incremental and Cyclic Repetition of List Elements
# using loop + enumerate()

# Initializing list
test_list = ['g', 'f', 'g', 'C', 'S']

# printing original list
print("The original list is : " + str(test_list))

# Initializing range
i, j = 2, 4

# Incremental and Cyclic Repetition of List Elements
# using loop + enumerate()
res = []
temp = list(range(i, j + 1))
for idx, ele in enumerate(test_list):
    res.append(ele * temp[idx % len(temp)])

# printing result
print ("Repetition List is : " + str(res))
```

**Output : **

```
The original list is : ['g', 'f', 'g', 'C', 'S']
Repetition List is : ['gg', 'fff', 'gggg', 'CC', 'SSS']
```

**方法 2:使用 cycle() + loop + zip()**
这些任务的组合也可以用来执行这个任务。在本文中，我们使用循环和循环进行迭代，并使用 cycle()执行重复。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Incremental and Cyclic Repetition of List Elements
# using cycle() + loop + zip()
from itertools import cycle

# Initializing list
test_list = ['g', 'f', 'g', 'C', 'S']

# printing original list
print("The original list is : " + str(test_list))

# Initializing range
i, j = 2, 4

# Incremental and Cyclic Repetition of List Elements
# using cycle() + loop + zip()
res = []
for k, l in zip(cycle(range(i, j + 1)), test_list):
    res.append(k * l)

# printing result
print ("Repetition List is : " + str(res))
```

**Output : **

```
The original list is : ['g', 'f', 'g', 'C', 'S']
Repetition List is : ['gg', 'fff', 'gggg', 'CC', 'SSS']
```