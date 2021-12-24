# Python |布尔列表初始化

> 原文:[https://www . geesforgeks . org/python-boolean-list-initialization/](https://www.geeksforgeeks.org/python-boolean-list-initialization/)

在编程中，我们经常需要用一些初始值来初始化一个列表。在动态编程中，这种方法使用得更频繁，主要要求是用布尔值 0 或 1 初始化。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解**
这可以用简单的方法轻松完成，因此，也可以用列表理解转换成紧凑版本。这是执行此任务的最基本方式。

```py
# Python3 code to demonstrate 
# to perform boolean list initializing 
# using list comprehension 

# using list comprehension 
# to perform boolean list initializing
res =  [True for i in range(6)]

# printing result
print ("The True initialized list is : " +  str(res))
```

**Output:**

```py
The True initialized list is : [True, True, True, True, True, True]

```