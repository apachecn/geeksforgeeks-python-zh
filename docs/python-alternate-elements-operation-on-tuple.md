# Python–元组上的替代元素操作

> 原文:[https://www . geesforgeks . org/python-alternate-elements-operation-on-tuple/](https://www.geeksforgeeks.org/python-alternate-elements-operation-on-tuple/)

有时，在使用 Python 元组时，我们可能会遇到这样的问题，即我们需要对提取的元组交替链执行操作。这种操作可以应用于许多领域，例如 web 开发。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = (5，6，3)
> **输出** :
> 交替链和 1 : 6
> 交替链和 2 : 8
> 
> **输入** : test_tuple = (5，6)
> **输出** :
> 交替链和 1 : 6
> 交替链和 2 : 5

**方法#1:使用 loop + `enumerate()`**
以上功能的组合为这个问题提供了蛮力解决方案。在本文中，我们使用枚举()提取元素和索引，并使用条件执行链接。

```py
# Python3 code to demonstrate working of 
# Alternate Elements operation on Tuple
# Using loop + enumerate()

# initializing tuple
test_tuple = (5, 6, 3, 6, 10, 34)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Alternate Elements operation on Tuple
# Using loop + enumerate()
sum1 = 0
sum2 = 0
for idx, ele in enumerate(test_tuple):
    if idx % 2:
        sum1 += ele
    else :
        sum2 += ele

# printing result 
print("The alternate chain sum 1 : " + str(sum1))
print("The alternate chain sum 2 : " + str(sum2)) 
```

**Output :**

```py
The original tuple : (5, 6, 3, 6, 10, 34)
The alternate chain sum 1 : 46
The alternate chain sum 2 : 18

```

**方法 2:使用列表切片**
这个问题也可以使用切片操作来执行。在本文中，我们使用列表切片技术来执行提取交替链的任务。

```py
# Python3 code to demonstrate working of 
# Alternate Elements operation on Tuple
# Using list slicing

# initializing tuple
test_tuple = (5, 6, 3, 6, 10, 34)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Alternate Elements operation on Tuple
# Using list slicing
sum1 = sum(test_tuple[1::2])
sum2 = sum(test_tuple[0::2])

# printing result 
print("The alternate chain sum 1 : " + str(sum1))
print("The alternate chain sum 2 : " + str(sum2)) 
```

**Output :**

```py
The original tuple : (5, 6, 3, 6, 10, 34)
The alternate chain sum 1 : 46
The alternate chain sum 2 : 18

```