# Python |从列表中获取唯一元组

> 原文:[https://www . geesforgeks . org/python-get-unique-元组-from-list/](https://www.geeksforgeeks.org/python-get-unique-tuples-from-list/)

有时，在使用 Python 列表时，我们会遇到一个问题，我们需要找到列表的唯一出现。拥有基本数据类型很容易处理，但有时，我们可能会有复杂的数据类型，在这种情况下，问题就变得新了。让我们讨论处理这个问题的元组的某些方法。

**方法#1:使用`list() + set()`**
相似的整数，这些整数是不可变的，也可以由`set()`处理以移除重复的。它将列表转换为 set 并移除重复项，然后由`list()`转换回列表

```
# Python3 code to demonstrate working of
# Get unique tuples from list
# using set() + list()

# initializing list
test_list = [(4, 5), (6, 1), (4, 5), (6, 1)]

# printing original list
print("The original list is : " + str(test_list))

# Get unique tuples from list
# using set() + list()
res = list(set(test_list))

# printing result 
print("List after removal of duplicates " + str(res))
```

**Output :**

```
The original list is : [(4, 5), (6, 1), (4, 5), (6, 1)]
List after removal of duplicates [(4, 5), (6, 1)]

```