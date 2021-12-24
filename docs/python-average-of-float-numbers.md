# Python |浮点数平均值

> 原文:[https://www . geesforgeks . org/python-浮点数平均值/](https://www.geeksforgeeks.org/python-average-of-float-numbers/)

在使用 Python 时，我们可能会遇到一个问题，即我们需要找到一个具有浮点元素的累积列表的平均值。这个问题在数据科学领域很常见。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环+公式**
处理这个问题的更简单的方式是使用求平均值的公式，并使用循环短指针来执行。这是解决这个问题最基本的方法。

```py
# Python3 code to demonstrate working of 
# Average of Float Numbers 
# using loop + formula 
import math

# initialize list 
test_list = [6.1, 7.2, 3.3, 9.4, 10.6, 15.7] 

# printing original list 
print("The original list is : " + str(test_list)) 

# Average of Float Numbers
# using loop + formula 
sum = 0
for ele in test_list:
  sum += ele
res = sum / len(test_list)

# printing result 
print("The mean of float list elements is : " + str(res)) 
```

**Output :**

```py
The original list is : [6.1, 7.2, 3.3, 9.4, 10.6, 15.7]
The mean of float list elements is : 8.716666666666667

```