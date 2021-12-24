# Python |交替后置迭代

> 原文:[https://www . geesforgeks . org/python-alternate-rear-iteration/](https://www.geeksforgeeks.org/python-alternate-rear-iteration/)

数字的迭代是通过 python 中的循环技术完成的。Python 中有许多促进循环的技术。有时我们需要以交替的方式向后执行循环，让人手不足的人这样做可能非常有用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`reversed()`**
最简单的方法是使用 for 循环的反函数，迭代将从后面开始，而不是传统的计数。

```py
# Python3 code to demonstrate 
# Alternate Rear iteration
# using reversed()

# Initializing number from which 
# iteration begins 
N = 6

# using reversed() to perform the Alternate Rear iteration
print ("The reversed numbers are : ", end = "")
for num in reversed(range(0, N + 1, 2)) :
    print (num, end = " ")
```

**Output :**

```py
The reversed numbers are : 6 4 2 0 

```