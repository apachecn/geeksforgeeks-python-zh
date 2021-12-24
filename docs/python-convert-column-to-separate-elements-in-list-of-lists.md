# Python |将列转换为列表列表中的单独元素

> 原文:[https://www . geeksforgeeks . org/python-convert-column-to-separate-elements-in-list-list/](https://www.geeksforgeeks.org/python-convert-column-to-separate-elements-in-list-of-lists/)

在某些情况下，我们可能需要提取矩阵的特定列，并将其每个值作为列表中的独立实体进行分配，这在机器学习领域中通常很有用。让我们讨论执行此操作的某些方式。
**方法#1:使用列表切片和列表理解**
可以将列表切片和理解的功能组合起来，执行从列表中提取一列的特定任务，然后使用列表理解将其添加为新元素。

## 蟒蛇 3

```
# Python3 code to demonstrate 
# column to separate elements in list of lists
# using list slicing and list comprehension

# initializing list of list
test_list = [[1, 3, 4],
             [6, 2, 8],
             [9, 10, 5]]

# printing original list
print ("The original list is : " + str(test_list))

# using list slicing and list comprehension
# column to separate elements in list of lists
res = [i for nest_list in [[j[1 : ], [j[0]]]
         for j in test_list] for i in nest_list]

# printing result
print ("The list after column shift is : " + str(res))
```

**Output**

```
The original list is : [[1, 3, 4], [6, 2, 8], [9, 10, 5]]
The list after column shift is : [[3, 4], [1], [2, 8], [6], [10, 5], [9]]

```

**方法 2:使用 itertools.chain() +列表理解+列表切片**
通过引入元素链的概念，可以改进上述方法，减少列表理解的开销，减少执行这个特定任务所花费的时间。

## 蟒蛇 3

```
# Python3 code to demonstrate 
# column to separate elements in list of lists
# using itertools.chain()+ list comprehension + list slicing
from itertools import chain

# initializing list of list
test_list = [[1, 3, 4],
             [6, 2, 8],
             [9, 10, 5]]

# printing original list
print ("The original list is : " + str(test_list))

# using itertools.chain() + list comprehension + list slicing
# column to separate elements in list of lists
res = list(chain(*[list((sub[1: ], [sub[0]]))
                      for sub in test_list]))

# printing result
print ("The list after column shift is : " + str(res))
```

**Output**

```
The original list is : [[1, 3, 4], [6, 2, 8], [9, 10, 5]]
The list after column shift is : [[3, 4], [1], [2, 8], [6], [10, 5], [9]]

```