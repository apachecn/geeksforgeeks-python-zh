# Python–布尔列表中的错误索引

> 原文:[https://www . geesforgeks . org/python-false-indexs-in-a-boolean-list/](https://www.geeksforgeeks.org/python-false-indices-in-a-boolean-list/)

开发人员经常使用布尔列表在散列过程中检查假值。这些在开发者日常生活中有很多应用。布尔列表也用于动态编程中的某些动态编程范例。也在值的机器学习预处理中。让我们讨论在 Python 中获取列表中错误值的索引的某些方法。

**方法#1:使用`enumerate()`和列表理解**
枚举()可以用其值做散列索引的任务，加上列表理解可以让我们检查错误的值。

```py
# Python3 code to demonstrate 
# False indices
# using enumerate() + list comprehension

# initializing list 
test_list = [True, False, True, False, True, True, False]

# printing original list 
print ("The original list is : " + str(test_list))

# using enumerate() + list comprehension
# False indices
res = [i for i, val in enumerate(test_list) if not val]

# printing result
print ("The list indices having False values are : " + str(res))
```

**Output :**

```py
The original list is : [True, False, True, False, True, True, False]
The list indices having False values are : [1, 3, 6]

```