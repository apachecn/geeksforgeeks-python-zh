# Python–检查元组是否只包含 K 个元素

> 原文:[https://www . geesforgeks . org/python-check-if-tuple-contains-only-k-elements/](https://www.geeksforgeeks.org/python-check-if-tuple-contains-only-k-elements/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要测试任何元组是否包含来自集合 K 元素的元素。这种问题很常见，在 web 开发和日常编程等许多领域都有应用。让我们讨论一下完成这项任务的某些方法。

> **输入** : test_tuple = (1，2，3，2，1，2)，K = [1，2，3，4]
> **输出**:真
> 
> **输入** : test_tuple = (1，2，3)，K = [1，2]
> 输出 : False

**方法#1:使用`all()`**
这是可以执行此任务的方式之一。在这种情况下，我们使用内置函数 all()检查元组中所有元素是否都来自特定的数字集。

```py
# Python3 code to demonstrate working of 
# Check if Tuple contains only K elements
# Using all()

# initializing tuple
test_tuple = (3, 5, 6, 5, 3, 6)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# initializing K elements
K = [3, 6, 5]

# Check if Tuple contains only K elements
# Using all()
res = all(ele in K for ele in test_tuple)

# printing result 
print("Does tuples contains just from K elements : " + str(res))
```

**Output :**

```py
The original tuple : (3, 5, 6, 5, 3, 6)
Does tuples contains just from K elements : True

```

**方法 2:使用`set()`**
这是解决这个问题的又一种方法。在这种情况下，我们将元组转换为集合，然后测试与查询 K 个元素的小于等于关系。

```py
# Python3 code to demonstrate working of 
# Check if Tuple contains only K elements
# Using set()

# initializing tuple
test_tuple = (3, 5, 6, 5, 3, 6)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# initializing K elements
K = [3, 6, 5]

# Check if Tuple contains only K elements
# Using all()
res = set(test_tuple) <= set(K)

# printing result 
print("Does tuples contains just from K elements : " + str(res))
```

**Output :**

```py
The original tuple : (3, 5, 6, 5, 3, 6)
Does tuples contains just from K elements : True

```