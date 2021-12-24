# Python |在列表开头添加列表

> 原文:[https://www . geesforgeks . org/python-列表开头添加列表/](https://www.geeksforgeeks.org/python-add-list-at-beginning-of-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，需要向其他列表添加一个完整的列表。列表的后端添加之前已经讨论过了。但是有时，我们需要在列表的开头执行追加。让我们讨论执行这项任务的某些方法。

**方法#1:使用 `"+" operator`**
可以使用“+”运算符来执行该特定任务。在这种情况下，我们只需先添加一个列表，然后构建一个新的列表或添加到同一个列表中。

```
# Python3 code to demonstrate working of
# Adding list at beginning of list
# using "+" operator

# initialize list
test_list = [1, 4, 5, 7, 6]

# initialize add list
add_list = [3, 4, 2, 10]

# printing original list
print("The original list is : " + str(test_list))

# printing add list 
print("The add list is : " + str(add_list))

# Adding list at beginning of list
# using "+" operator
test_list = add_list + test_list

# printing result
print("The original updated list is : " + str(test_list))
```

**Output :**

```
The original list is : [1, 4, 5, 7, 6]
The add list is : [3, 4, 2, 10]
The original updated list is : [3, 4, 2, 10, 1, 4, 5, 7, 6]

```