# Python–自定义列矩阵

> 原文:[https://www.geeksforgeeks.org/python-custom-columns-matrix/](https://www.geeksforgeeks.org/python-custom-columns-matrix/)

有时，在使用 Python 列表时，我们会遇到一个问题，即我们需要从 Matrix 中提取某些列并重新创建它。这种问题在数据领域也有应用，因为它们使用矩阵作为突出的输入参数。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [[5，4，3，4]，[7，6，3，2]，[8，3，9，10]]，col_list = [2]
> **输出** : [[3]，[3]，[9]]
> 
> **输入** : test_list = [[5，4]，[6，2]，[8，3]]，col_list = [1]
> **输出** : [[4]，[2]，[3]]

**方法#1:使用列表理解**
这提供了解决这个问题的方法之一。在本文中，我们使用嵌套列表理解来执行选择性列的提取。

```
# Python3 code to demonstrate working of 
# Custom Columns Matrix
# Using list comprehension

# initializing list
test_list = [[5, 4, 3, 4],
             [7, 6, 3, 2], 
             [8, 3, 9, 10]]

# printing original list 
print("The original list : " + str(test_list))

# initializing Columns list 
col_list = [1, 3]

# Custom Columns Matrix
# Using list comprehension
res = [[sub[idx] for idx in col_list] for sub in test_list]

# printing result 
print("Matrix after filtering : " + str(res))
```

**Output :**

```
The original list : [[5, 4, 3, 4], [7, 6, 3, 2], [8, 3, 9, 10]]
Matrix after filtering : [[4, 4], [6, 2], [3, 10]]

```

**方法二:使用`itemgetter()` +列表理解**
以上功能的组合可以解决这个问题。在本文中，我们使用 itemgetter()执行获取索引的任务。

```
# Python3 code to demonstrate working of 
# Custom Columns Matrix
# Using itemgetter() + list comprehension
from operator import itemgetter

# initializing list
test_list = [[5, 4, 3, 4],
             [7, 6, 3, 2], 
             [8, 3, 9, 10]]

# printing original list 
print("The original list : " + str(test_list))

# initializing Columns list 
col_list = [1, 3]

# Custom Columns Matrix
# Using itemgetter() + list comprehension
res = [list(itemgetter(*col_list)(ele)) for ele in test_list]

# printing result 
print("Matrix after filtering : " + str(res))
```

**Output :**

```
The original list : [[5, 4, 3, 4], [7, 6, 3, 2], [8, 3, 9, 10]]
Matrix after filtering : [[4, 4], [6, 2], [3, 10]]

```