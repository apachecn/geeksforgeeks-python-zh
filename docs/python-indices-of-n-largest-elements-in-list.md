# Python |列表中 N 个最大元素的索引

> 原文:[https://www . geesforgeks . org/python-indexs-of-n-最大列表元素/](https://www.geeksforgeeks.org/python-indices-of-n-largest-elements-in-list/)

有时候，在使用 Python 列表时，我们可能会遇到一个问题，我们希望找到 N 个最大的元素。这项工作可以在许多领域进行，例如网页开发和使用数据库。我们有时可能需要找到它们的索引。让我们讨论在列表中找到 N 个最大元素的索引的特定方法。

**方法:使用`sorted()` + lambda +列表切片**
该任务可以使用以上功能的组合来执行。在这种情况下，`sorted()`可用于获取容器，需要在后端获取 N 个最大的元素，然后使用列表切片来计算索引。

```
# Python3 code to demonstrate working of
# Indices of N largest elements in list
# using sorted() + lambda + list slicing

# initialize list
test_list = [5, 6, 10, 4, 7, 1, 19]

# printing original list
print("The original list is : " + str(test_list))

# initialize N 
N = 4

# Indices of N largest elements in list
# using sorted() + lambda + list slicing
res = sorted(range(len(test_list)), key = lambda sub: test_list[sub])[-N:]

# printing result
print("Indices list of max N elements is : " + str(res))
```

**Output :**

```
The original list is : [5, 6, 10, 4, 7, 1, 19]
Indices list of max N elements is : [1, 4, 2, 6]

```