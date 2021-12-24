# Python |将元组列表展平为字符串

> 原文:[https://www . geesforgeks . org/python-扁平化-元组-列表到字符串/](https://www.geeksforgeeks.org/python-flatten-tuples-list-to-string/)

有时，在处理数据时，我们可能会遇到需要执行数据相互转换的问题。在这种情况下，我们可能会遇到将元组列表转换为单个字符串的问题。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `join()`**
上述功能的组合可用于执行该任务。在这种情况下，我们使用`join()`连接所有单独的字符串元素，并使用列表理解来提取每个元素。

```py
# Python3 code to demonstrate working of
# Flatten Tuples List to String
# using join() + list comprehension

# initialize list of tuple
test_list = [('1', '4', '6'), ('5', '8'), ('2', '9'), ('1', '10')]

# printing original tuples list
print("The original list : " + str(test_list))

# Flatten Tuples List to String
# using join() + list comprehension
res = ' '.join([idx for tup in test_list for idx in tup])

# printing result
print("Tuple list converted to String is : " + res)
```

**Output :**

```py
The original list : [('1', '4', '6'), ('5', '8'), ('2', '9'), ('1', '10')]
Tuple list converted to String is : 1 4 6 5 8 2 9 1 10

```