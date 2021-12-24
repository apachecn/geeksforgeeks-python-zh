# Python |将列表列表转换成树状字典

> 原文:[https://www . geesforgeks . org/python-convert-a-list-list-to-tree-like-dict/](https://www.geeksforgeeks.org/python-convert-a-list-of-lists-into-tree-like-dict/)

给定一个列表列表，编写一个 Python 程序，将给定的列表列表转换成树状字典。

**示例:**

```
Input : [[1], [2, 1], [3, 1], [4, 2, 1], [5, 2, 1], [6, 3, 1], [7, 3, 1]]
Output : {1: {2: {4: {}, 5: {}}, 3: {6: {}, 7: {}}}}

Input : [['A'], ['B', 'A'], ['C', 'A'], ['D', 'C', 'A']]
Output : {'A': {'C': {'D': {}}, 'B': {}}}

```

**方法#1 :** 天真方法
这是一种天真的方法，其中我们使用两个 for 循环遍历列表列表。我们将空字典“树”初始化为 *currTree* ，并且每次我们检查关键字(列表的项目列表)是否包含在 *currTree* 中。如果没有，将其包含在 *currTree* 中，否则不做任何事情。最后，将`currTree[key]`分配给`currTree`。

```
# Python3 program to Convert a list
# of lists into Dictionary (Tree form)

def formTree(list):
    tree = {}
    for item in list:
        currTree = tree

        for key in item[::-1]:
            if key not in currTree:
                currTree[key] = {}
            currTree = currTree[key]

    return tree

# Driver Code
lst = [['A'], ['B', 'A'], ['C', 'A'], ['D', 'C', 'A']]
print(formTree(lst))
```

**Output:**

```
{'A': {'B': {}, 'C': {'D': {}}}}

```

**方法#2 :** 使用`reduce()`
`reduce()`函数用于将参数中传递的特定函数应用于传递序列中提到的所有列表元素。我们将使用`reduce()`遍历字典，并重新使用`getTree()`找到存储`setTree()`值的位置。需要*映射列表*中除最后一个元素之外的所有元素来找到要添加值的“父”字典，然后使用最后一个元素将值设置为正确的键。

```
# Python3 program to Convert a list
# of lists into Dictionary (Tree form)

from functools import reduce
from operator import getitem

def getTree(tree, mappings):
    return reduce(getitem, mappings, tree)

def setTree(tree, mappings):
    getTree(tree, mappings[:-1])[mappings[-1]] = dict()

# Driver Code
lst = [['A'], ['B', 'A'], ['C', 'A'], ['D', 'C', 'A']]
tree ={}
for item in lst:
    setTree(tree, item[::-1])

print(tree)
```

**Output:**

```
{'A': {'B': {}, 'C': {'D': {}}}}

```