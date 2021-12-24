# Python–在矩阵中添加自定义维度

> 原文:[https://www . geesforgeks . org/python-add-custom-dimension-in-matrix/](https://www.geeksforgeeks.org/python-add-custom-dimension-in-matrix/)

有时，在使用 Python Matrix 时，我们可能会遇到一个问题，即我们需要添加另一个维度的自定义值，这种问题可能在各种领域都有问题，例如日常编程和竞争性编程。让我们讨论执行这项任务的某些方法。

> **输入** :
> 测试 _ 列表= [(5，6，7，8)]
> val =[10]
> **输出** : [(5，6，7，8，10)]
> 
> **输入** :
> test_list = [(5，，(6)、(7)、(8)、]
> val =[10，9，8，7]
> **输出** : [(5，10)，(6，9)，(7，8)，(8，7)]

**方法一:使用`zip()` +列表理解+“+”运算符**
以上功能的组合可以解决这个问题。在本例中，我们使用+运算符添加一个元素，并使用 zip()将该逻辑扩展到 Matrix 的每一行。

```
# Python3 code to demonstrate working of 
# Add custom dimension in Matrix
# Using zip() + list comprehension + "+" operator

# initializing list
test_list = [(5, 6), (1, 2), (7, 8), (9, 12)]

# printing original list
print("The original list is : " + str(test_list))

# initializing Column values 
vals = [4, 5, 7, 3]

# Add custom dimension in Matrix
# Using zip() + list comprehension + "+" operator
res = [i + (j, ) for i, j in zip(test_list, vals)]

# printing result 
print("The result after adding dimension : " + str(res)) 
```

**Output :**

```
The original list is : [(5, 6), (1, 2), (7, 8), (9, 12)]
The result after adding dimension : [(5, 6, 4), (1, 2, 5), (7, 8, 7), (9, 12, 3)]

```

**方法 2:使用`zip() + * operator`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用解包操作符执行 joinig 的任务来解包值，然后执行自定义值的 join。

```
# Python3 code to demonstrate working of 
# Add custom dimension in Matrix
# Using zip() + * operator

# initializing list
test_list = [(5, 6), (1, 2), (7, 8), (9, 12)]

# printing original list
print("The original list is : " + str(test_list))

# initializing Column values 
vals = [4, 5, 7, 3]

# Add custom dimension in Matrix
# Using zip() + * operator
res = [(*i, j) for i, j in zip(test_list, vals)]

# printing result 
print("The result after adding dimension : " + str(res)) 
```

**Output :**

```
The original list is : [(5, 6), (1, 2), (7, 8), (9, 12)]
The result after adding dimension : [(5, 6, 4), (1, 2, 5), (7, 8, 7), (9, 12, 3)]

```