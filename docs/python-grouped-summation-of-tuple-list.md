# Python |元组列表分组求和

> 原文:[https://www . geesforgeks . org/python-group-summary-of-tuple-list/](https://www.geeksforgeeks.org/python-grouped-summation-of-tuple-list/)

很多时候，我们会得到一个元组列表，我们需要对它的键进行分组，并在分组时执行某些操作。最常见的操作是加法。让我们讨论执行这项任务的某些方法。除了加法，其他操作也可以通过做一些小的改变来完成。

**方法:使用`Counter()`+`"+" operator`+T3】**

此任务可以使用计数器功能来执行，因为它在内部进行分组，加法运算符可用于指定分组结果的功能。

```
# Python3 code to demonstrate
# group summation of tuple list 
# using Counter() + "+" operator
from collections import Counter

# initializing list of tuples
test_list1 = [('key1', 4), ('key3', 6), ('key2', 8)]
test_list2 = [('key2', 1), ('key1', 4), ('key3', 2)]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using Counter() + "+" operator
# group summation of tuple list 
cumul_1 = Counter(dict(test_list1))
cumul_2 = Counter(dict(test_list2))
cumul_3 = cumul_1 + cumul_2   
res = list(cumul_3.items())

# print result
print("The grouped summation tuple list is : " + str(res))
```

**输出:**

```
The original list 1 : [('key1', 4), ('key3', 6), ('key2', 8)]
The original list 2 : [('key2', 1), ('key1', 4), ('key3', 2)]
The grouped summation tuple list is : [('key2', 9), ('key1', 8), ('key3', 8)]

```