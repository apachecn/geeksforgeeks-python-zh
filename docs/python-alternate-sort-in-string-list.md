# Python |字符串列表中的替代排序

> 原文:[https://www . geesforgeks . org/python-alternate-sort-in-string-list/](https://www.geeksforgeeks.org/python-alternate-sort-in-string-list/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们只需要在列表中交替执行排序。这种应用可以出现很多次。让我们讨论一下执行这项任务的具体方法。

**方法:使用`join() + enumerate()` +生成器表达式+ `sorted()`**
这个任务可以通过使用上面的功能组合来实现。在本例中，我们仅使用字符串列表中的%2 个元素来执行排序。此操作扩展到整个列表是由生成器表达式执行的。

```
# Python3 code to demonstrate working of
# Alternate Sort String list 
# using join() + enumerate() + generator expression + sorted()

# initialize list 
test_list = ['cdab', 'gfeh', 'kjil']

# printing original list 
print("The original list : " + str(test_list))

# Alternate Sort String list 
# using join() + enumerate() + generator expression + sorted()
res = ["".join(sorted(j, reverse = i % 2)) for i, j in enumerate(test_list)] 

# printing result
print("The String list after alternate sorting : " + str(res))
```

**Output :**

```
The original list : ['cdab', 'gfeh', 'kjil']
The String list after alternate sorting : ['abcd', 'hgfe', 'ijkl']

```