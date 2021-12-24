# Python |在列表列表中找到每个索引的最小值

> 原文:[https://www . geeksforgeeks . org/python-查找列表中每个索引的最小值/](https://www.geeksforgeeks.org/python-find-minimum-of-each-index-in-list-of-lists/)

有时，我们会遇到这样的问题，我们需要找到矩阵中每列的**最小值，即列表中每个索引的最小值。这种问题在竞争性编程中很常见，也很有用。让我们讨论一下解决这个问题的某些方法。**

**示例:**

```
Input : [[3, 7, 6], [1, 3, 5], [9, 3, 2]]
Output : [1, 3, 2] 

Input : [[3, 2, 8], [5, 3, 5], [9, 3, 1]] 
Output : [3, 2, 1]

```

**方法#1:使用`min() + list comprehension + zip()`**

解决这个特殊问题需要上述方法的结合。min 函数用于获取所需的最小值，zip 函数提供相似索引的组合，然后使用列表理解创建列表。

```
# Python3 code to demonstrate
# Minimum index value
# using min() + list comprehension + zip()

# initializing list
test_list = [[3, 7, 6], [1, 3, 5], [9, 3, 2]]

# printing original list
print("The original list : " + str(test_list))

# using min() + list comprehension + zip()
# Minimum index value
res = [min(idx) for idx in zip(*test_list)]

# print result
print("The Minimum of each index list is : " + str(res))
```

**Output :**

```
The original list : [[3, 7, 6], [1, 3, 5], [9, 3, 2]]
The Minimum of each index list is : [1, 3, 2]

```

**方法 2:使用`map() + min() + zip()`**

这与上述方法的工作方式几乎相似，但不同之处只是我们使用 map 函数来构建 min 元素列表，而不是使用列表理解。

```
# Python3 code to demonstrate
# Minimum index value
# using min() + map() + zip()

# initializing list
test_list = [[3, 7, 6], [1, 3, 5], [9, 3, 2]]

# printing original list
print("The original list : " + str(test_list))

# using min() + map() + zip()
# Minimum index value
res = list(map(min, zip(*test_list)))

# print result
print("The Minimum of each index list is : " + str(res))
```

**Output :**

```
The original list : [[3, 7, 6], [1, 3, 5], [9, 3, 2]]
The Minimum of each index list is : [1, 3, 2]

```