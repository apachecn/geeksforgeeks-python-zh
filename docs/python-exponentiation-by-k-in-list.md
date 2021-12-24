# Python |列表中 K 的幂运算

> 原文:[https://www . geeksforgeeks . org/python-按列表中的 k 取幂/](https://www.geeksforgeeks.org/python-exponentiation-by-k-in-list/)

在使用 python 列表时，我们会遇到这样一种情况，我们需要对列表中的每个元素进行指数常量。我们可能需要对每个元素进行迭代和指数常量，但是这会增加代码的行数。让我们讨论一下执行这项任务的某些人手不足的情况。

**方法#1:使用列表理解**
列表理解只是执行我们使用天真方法执行的任务的简单方法。这主要有助于节省时间，在代码可读性方面也是最好的。

```
# Python3 code to demonstrate 
# Exponentiation by K in list
# using list comprehension

# initializing list 
test_list = [4, 5, 6, 3, 9]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K
K = 4

# using list comprehension
# Exponentiation by K in list
res = [x ** K for x in test_list]

# printing result 
print ("The list after constant exponentiation : " + str(res))
```

**Output :**

```
The original list is : [4, 5, 6, 3, 9]
The list after constant exponentiation : [256, 625, 1296, 81, 6561]

```