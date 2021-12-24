# Python–列表上的常数乘法

> 原文:[https://www . geesforgeks . org/python-常量-乘法-over-list/](https://www.geeksforgeeks.org/python-constant-multiplication-over-list/)

在使用 python 列表时，我们会遇到这样一种情况，即我们需要将常数乘以列表中的每个元素。我们可能需要对每个元素进行迭代和乘常数，但这会增加代码的行数。让我们讨论一下执行这项任务的某些人手不足的情况。

**方法#1:使用列表理解**
列表理解只是执行我们使用天真方法执行的任务的简单方法。这主要有助于节省时间，在代码可读性方面也是最好的。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Constant Multiplication over List
# using list comprehension

# initializing list
test_list = [4, 5, 6, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K
K = 4

# using list comprehension
# Constant Multiplication over List
res = [x * K for x in test_list]

# printing result
print ("The list after constant multiplication : " + str(res))
```

**Output**

```
The original list is : [4, 5, 6, 3, 9]
The list after constant multiplication : [16, 20, 24, 12, 36]
```

**方法 2:使用 map() + operator.mul**
这与上面的函数类似，但是使用 operator.mul 将每个元素乘以在应用 map 函数之前形成的另一个 K 列表中的其他元素。它将列表中相似的索引元素相乘。

## 蟒蛇 3

```
# Python3 code to demonstrate
# Constant Multiplication over List
# using map() + operator.mul
import operator

# initializing list
test_list = [4, 5, 6, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K list
K_list = [4] * len(test_list)

# using map() + operator.mul
# Constant Multiplication over List
res = list(map(operator.mul, test_list, K_list))

# printing result
print ("The list after constant multiplication : " + str(res))
```

**Output**

```
The original list is : [4, 5, 6, 3, 9]
The list after constant multiplication : [16, 20, 24, 12, 36]

```