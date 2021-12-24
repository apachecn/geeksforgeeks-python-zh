# Python–从给定前缀

开始过滤列表元素

> 原文:[https://www . geesforgeks . org/python-filter-list-elements-以给定前缀开头/](https://www.geeksforgeeks.org/python-filter-list-elements-starting-with-given-prefix/)

有时，我们需要用列表中每个字符串的第一个字符来过滤列表。这种类型的任务在日常编程甚至在竞争性编程领域都有许多应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ startswith()**
在这个方法中，我们使用列表理解进行遍历逻辑，使用 startswith 方法过滤掉所有以特定字母开头的字符串。剩余的字符串可用于制作不同的列表。

```py
# Python3 code to demonstrate
# Prefix Separation
# Using list comprehension + startswith()

# initializing list
test_list = ['sapple', 'orange', 'smango', 'grape']

# initializing start Prefix
start_letter = 's'

# printing original list
print("The original list : " + str(test_list))

# using list comprehension + startswith()
# Prefix Separation
with_s = [x for x in test_list if x.startswith(start_letter)]
without_s = [x for x in test_list if x not in with_s]

# print result
print("The list without prefix s : " + str(without_s))
print("The list with prefix s : " + str(with_s))
```

**Output :**

```py
The original list : ['sapple', 'orange', 'smango', 'grape']
The list without prefix s : ['orange', 'grape']
The list with prefix s : ['sapple', 'smango']

```