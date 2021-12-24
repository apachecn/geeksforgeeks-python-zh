# Python–指数值求和列表

> 原文:[https://www . geesforgeks . org/python-index-value-summary-list/](https://www.geeksforgeeks.org/python-index-value-summation-list/)

要访问列表的元素，有多种方法。但有时我们可能需要访问元素及其索引，并计算其总和，为此，我们可能需要采用不同的策略。本文将讨论其中的一些策略。

**方法 1:幼稚方法**
这是最通用的方法，可以用来执行访问索引和列表元素值的任务。这是使用循环完成的。执行求和的任务是使用外部变量相加来执行的。

```
# Python 3 code to demonstrate 
# Index Value Summation List
# using naive method

# initializing list
test_list = [1, 4, 5, 6, 7]

# Printing list 
print ("The original list is : " + str(test_list))

# using naive method to
# Index Value Summation List
res = []
for i in range(len(test_list)):
    res.append(i + test_list[i])

print ("The list index-value summation is : " + str(res))
```

**Output :**

```
The original list is : [1, 4, 5, 6, 7]
The list index-value summation is : [1, 5, 7, 9, 11]

```