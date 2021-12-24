# Python |检查两个元组列表是否相同

> 原文:[https://www . geesforgeks . org/python-检查二元组列表是否相同/](https://www.geeksforgeeks.org/python-check-if-two-list-of-tuples-are-identical/)

有时，在处理元组时，我们可能会遇到这样的问题，即我们有一个元组列表，我们需要测试它们是否完全相同。这是一个非常基本的问题，可以发生在任何领域。让我们讨论一下完成这项任务的某些方法。

**方法一:使用 `==` 操作符**
这是执行这个任务最简单优雅的方式。它还检查元组索引彼此是否相等。

```py
# Python3 code to demonstrate working of
# Check if two list of tuples are identical
# using == operator

# initialize list of tuples 
test_list1 = [(10, 4), (2, 5)]
test_list2 = [(10, 4), (2, 5)]

# printing original tuples lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Check if two list of tuples are identical
# using == operator
res = test_list1 == test_list2

# printing result
print("Are tuple lists identical ? : " + str(res))
```

**Output :**

```py
The original list 1 : [(10, 4), (2, 5)]
The original list 2 : [(10, 4), (2, 5)]
Are tuple lists identical ? : True

```