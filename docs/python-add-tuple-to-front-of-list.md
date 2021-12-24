# Python |在列表前面添加元组

> 原文:[https://www . geesforgeks . org/python-添加元组到列表前面/](https://www.geeksforgeeks.org/python-add-tuple-to-front-of-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即需要向现有列表中添加一个新的元组。在后面追加通常比在前面追加容易。让我们讨论执行这项任务的某些方法。

**方法#1:使用`insert()`**
这是可以将元素一字排开添加到前面的方法之一。它用于在列表前面添加任何元素。元组的行为也一样。

```py
# Python3 code to demonstrate working of
# Adding tuple to front of list
# using insert()

# Initializing list 
test_list = [('is', 2), ('best', 3)]

# printing original list 
print("The original list is : " + str(test_list))

# Initializing tuple to add 
add_tuple = ('gfg', 1)

# Adding tuple to front of list
# using insert()
test_list.insert(0, add_tuple)

# printing result
print("The tuple after adding is : " + str(test_list))
```

**Output :**

```py
The original list is : [('is', 2), ('best', 3)]
The tuple after adding is : [('gfg', 1), ('is', 2), ('best', 3)]

```