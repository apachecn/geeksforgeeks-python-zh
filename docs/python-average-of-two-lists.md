# Python |两个列表的平均值

> 原文:[https://www.geeksforgeeks.org/python-average-of-two-lists/](https://www.geeksforgeeks.org/python-average-of-two-lists/)

在列表中找到平均值的问题很常见。但是有时这个问题可以扩展为两个列表，因此变成了一个修正的问题。本文讨论了容易执行这项任务的人手不足问题。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`sum() + len() + “+” operato` r**
通过 python 的常规 sum()和 len 函数可以确定平均值，使用“+”运算符可以处理一到两个列表的扩展。

```py
# Python3 code to demonstrate
# Average of two lists
# using sum() + len() + "+" operator

# initializing lists
test_list1 = [1, 3, 4, 5, 2, 6]
test_list2 = [3, 4, 8, 3, 10, 1]

# printing the original lists
print ("The original list 1 is : " + str(test_list1))
print ("The original list 2 is : " + str(test_list2))

# Average of two lists
# using sum() + len() + "+" operator
res = sum(test_list1 + test_list2) / len(test_list1 + test_list2)

# printing result
print ("The Average of both lists is : " + str(res))
```

**Output :**

```py
The original list 1 is : [1, 3, 4, 5, 2, 6]
The original list 2 is : [3, 4, 8, 3, 10, 1]
The Average of both lists is : 4.166666666666667

```