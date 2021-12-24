# Python–找到 k 个最小元素的索引

> 原文:[https://www . geeksforgeeks . org/python-find-the-indexes-for-k-minist-elements/](https://www.geeksforgeeks.org/python-find-the-indices-for-k-smallest-elements/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，我们希望找到 K 个最小元素的索引。这项工作可以在许多领域进行，例如网页开发和使用数据库。我们有时可能需要找到它们的索引。让我们讨论一种确定列表中 K 个最小元素的索引的方法。

**使用`sorted()`+λ+列表切片**

可以使用上述功能的组合来执行该任务。在这种情况下， `sorted()`可用于获取容器，需要在前端获取 K 个最小元素，然后使用列表切片计算索引。

```py
# Python3 code to demonstrate working of
# Smallest K elements indices
# using sorted() + lambda + list slicing

# initialize list
test_list = [5, 6, 10, 4, 7, 1, 19]

# printing original list
print("The original list is : " + str(test_list))

# initialize K
K = 3

# Smallest K elements indices
# using sorted() + lambda + list slicing
res = sorted(range(len(test_list)), key = lambda sub: test_list[sub])[:K]

# printing result
print("Indices list of min K elements is : " + str(res))
```

**输出:**

```py
The original list is : [5, 6, 10, 4, 7, 1, 19]
Indices list of min K elements is : [5, 3, 0]

```