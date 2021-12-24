# Python |列表中第一个非空字符串

> 原文:[https://www . geesforgeks . org/python-first-非空-列表中的字符串/](https://www.geeksforgeeks.org/python-first-non-empty-string-in-list/)

有时在处理数据科学时，我们需要处理大量数据，因此我们可能需要人手不足来执行某些任务。我们在预处理阶段处理空值，因此有时需要检查第一个有效元素。让我们讨论一下找到第一个非空字符串的某些方法。

**方法#1:使用`next()` +列表理解**
下一个函数返回迭代器，因此使用检查最后一个无值的列表理解来处理传统的列表理解和逻辑部分更有效。

```py
# Python3 code to demonstrate
# First Non-Empty String in list
# using next() + list comprehension

# initializing list
test_list = ["", "", "Akshat", "Nikhil"]

# printing original list 
print("The original list : " + str(test_list))

# using next() + list comprehension
# First Non-Empty String in list
res = next(sub for sub in test_list if sub)

# printing result
print("The first non empty string is : " + str(res))
```

**Output :**

```py
The original list : ['', '', 'Akshat', 'Nikhil']
The first non empty string is : Akshat

```