# Python 中的向后迭代

> 原文:[https://www.geeksforgeeks.org/backward-iteration-in-python/](https://www.geeksforgeeks.org/backward-iteration-in-python/)

数字的迭代是通过 Python 中的循环技术来完成的。Python 中有许多促进循环的技术。有时，我们需要执行反向循环，让人手不足的人这样做可能非常有用。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`reversed()`**
最简单的方法是对`for`循环使用反向函数，迭代将从后面开始，而不是传统的计数。

```py
# Python3 code to demonstrate 
# backward iteration
# using reversed()

# Initializing number from which 
# iteration begins 
N = 6

# using reversed() to perform the back iteration
print ("The reversed numbers are : ", end = "")
for num in reversed(range(N + 1)) :
    print (num, end = " ")
```

**Output :**

```py
The reversed numbers are : 6 5 4 3 2 1 0 

```