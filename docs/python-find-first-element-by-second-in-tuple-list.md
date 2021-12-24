# Python–在元组列表中按第二个查找第一个元素

> 原文:[https://www . geesforgeks . org/python-按元组列表中的第二个元素逐个查找/](https://www.geeksforgeeks.org/python-find-first-element-by-second-in-tuple-list/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即我们需要从给定的第二个元素中找到元组的第一个元素。这种问题可能发生在 web 开发等领域。让我们讨论执行这项任务的某些方法。

> **输入** :
> test_list = [(4，5)，(5，6)，(1，3)，(6，6)]
> K = 6
> T5】输出:【5，6】
> **输入** :
> test_list = [(4，5)，(5，7)，(1，3)，(6，8)]
> K = 6
> **输出** : []

**方法#1:使用列表理解**
这是执行这个任务的方法之一。在这种情况下，我们对每个元组进行迭代，如果找到与值匹配的键，我们就存储在结果列表中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Find first element by second in tuple List
# Using list comprehension

# initializing list
test_list = [(4, 5), (5, 6), (1, 3), (6, 9)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 6

# Find first element by second in tuple List
# Using list comprehension
res = [x for (x, y) in test_list if y == K]

# printing result
print("The key from value : " + str(res))
```

**Output : **

```
The original list is : [(4, 5), (5, 6), (1, 3), (6, 9)]
The key from value : [5]
```

**方法#2:使用 next() +生成器表达式**
这是解决这个任务的又一种方法。在这里，next()用于获取连续的元素，生成器表达式用于检查逻辑。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Find first element by second in tuple List
# Using next() + generator expression

# initializing list
test_list = [(4, 5), (5, 6), (1, 3), (6, 9)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 6

# Find first element by second in tuple List
# Using next() + generator expression
res = next((x for x, y in test_list if y == K), None)

# printing result
print("The key from value : " + str(res))
```

**Output : **

```
The original list is : [(4, 5), (5, 6), (1, 3), (6, 9)]
The key from value : 5
```