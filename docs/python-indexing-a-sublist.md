# Python |索引子列表

> 原文:[https://www.geeksforgeeks.org/python-indexing-a-sublist/](https://www.geeksforgeeks.org/python-indexing-a-sublist/)

在 Python 中，我们有几种方法来执行列表中的索引，但是有时，我们要索引的不仅仅是一个元素，真正的问题始于我们有一个子列表，并且它的元素必须被索引。让我们讨论一下实现这一点的某些方法。

**方法一:使用`index()` +列表理解**
这个方法分两部分解决这个问题，第一部分生成一个新的列表，然后对其进行索引。

```py
# Python3 code to demonstrate
# indexing of sublist 
# using list comprehension + index()

# initializing test list
test_list = [[1, 'Geeks'], [2, 'For'], [3, 'Geeks']]

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + index()
# indexing of sublist
res = [ele for i, ele in test_list].index('For')

# print result
print("Index of nested element is : " + str(res))
```

**Output :**

```py
The original list : [[1, 'Geeks'], [2, 'For'], [3, 'Geeks']]
Index of nested element is : 1

```