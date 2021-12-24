# Python |检查两个列表是否有任何共同的元素

> 原文:[https://www . geesforgeks . org/python-检查两个列表是否有任何共同元素/](https://www.geeksforgeeks.org/python-check-if-two-lists-have-any-element-in-common/)

有时我们会遇到检查一个列表是否包含另一个列表的任何元素的问题。这类问题在竞争性编程中相当普遍。让我们讨论实现这一特殊任务的各种方法。

**方法#1:** 使用`any()`

```
# Python code to check if two lists
# have any element in common

# Initialization of list
list1 = [1, 2, 3, 4, 55]
list2 = [2, 3, 90, 22]

# using any function
out = any(check in list1 for check in list2)

# Checking condition
if out:
    print("True") 
else :
    print("False")
```

**Output:**

```
True

```

**方法 2:** 使用 中的 ***运算符。***

```
# Python code to check if two lists
# have any element in common

# Initialization of list
list1 = [1, 3, 4, 55]
list2 = [90, 22]

flag = 0

# Using in to check element of
# second list into first list
for elem in list2:
    if elem in list1:
        flag = 1

# checking condition
if flag == 1:
    print("True") 
else :
    print("False")
```

**Output:**

```
False

```