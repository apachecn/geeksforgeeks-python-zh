# Python |检查列表中的所有元素是否符合条件

> 原文:[https://www . geesforgeks . org/python-检查列表中的所有元素是否符合条件/](https://www.geeksforgeeks.org/python-check-if-all-elements-in-list-follow-a-condition/)

有时候，在使用 Python 列表时，我们可能会遇到一个问题，我们需要检查列表中的所有元素是否都符合特定的条件。这可以在 web 开发领域的过滤中得到应用。让我们讨论执行这项任务的某些方法。

**方法一:使用`all()`**
我们可以使用`all()`，来执行这个特定的任务。在这种情况下，我们输入条件，所有元素的验证由`all()`内部检查。

```
# Python3 code to demonstrate working of
# Check if all elements in list follow a condition
# Using all()

# initializing list
test_list = [4, 5, 8, 9, 10]

# printing list
print("The original list : " + str(test_list))

# Check if all elements in list follow a condition
# Using all()
res = all(ele > 3 for ele in test_list)

# Printing result
print("Are all elements greater than 3 ? : " + str(res))
```

**Output :**

```

The original list : [4, 5, 8, 9, 10]
Are all elements greater than 3 ? : True

```