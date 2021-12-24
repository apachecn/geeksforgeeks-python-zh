# Python |在列表中的替代位置添加元素

> 原文:[https://www . geesforgeks . org/python-在列表中交替位置添加元素/](https://www.geeksforgeeks.org/python-add-element-at-alternate-position-in-list/)

有时候，在使用 Python 列表时，我们会遇到一个问题，我们需要在列表中交替添加元素，即在偶数位置，并相应地对列表进行重新排序。这在许多领域都有潜在的应用，比如日常编程和竞争性编程。让我们讨论一下解决这个问题的某些方法。

**方法:使用`join() + list()`**
这个方法可以一行解决这个问题。在这种情况下，我们只需将所有元素与目标元素交替连接，然后使用`list()`转换回列表。

```py
# Python3 code to demonstrate working of
# Add element at alternate position in list
# using join() + list()

# initialize list
test_list = ['a', 'b', 'c', 'd', 'e', 'f']

# printing original list
print("The original list is : " + str(test_list))

# initialize ele 
ele = '#'

# Add element at alternate position in list
# using join() + list()
res = list(ele.join(test_list))

# printing result
print("List after alternate addition : " + str(res))
```

**Output :**

```py
The original list is : ['a', 'b', 'c', 'd', 'e', 'f']
List after alternate addition : ['a', '#', 'b', '#', 'c', '#', 'd', '#', 'e', '#', 'f']

```