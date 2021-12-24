# Python |在嵌套列表中查找最大长度子列表

> 原文:[https://www . geesforgeks . org/python-find-最大长度-嵌套列表中的子列表/](https://www.geeksforgeeks.org/python-find-maximum-length-sub-list-in-a-nested-list/)

给定一个列表，编写一个 Python 程序来查找最大长度的列表。输出应为 *(list，list_length)* 形式。

**示例:**

```py
Input : [['A'], ['A', 'B'], ['A', 'B', 'C']]
Output : (['A', 'B', 'C'], 3)

Input : [[1, 2, 3, 9, 4], [5], [3, 8], [2]]
Output : ([1, 2, 3, 9, 4], 5)

```

我们来讨论一下解决这个问题的不同方法。

**方法#1 :** 使用 for 循环(幼稚)
这是一种蛮力方法，我们迭代每个列表项(列表)并找到最大长度的列表。同样，我们使用 for 循环来查找每个列表的长度，并输出最大长度。

```py
# Python3 program to Find maximum 
# length list in a nested list

def FindMaxLength(lst):
    maxList = max((x) for x in lst)
    maxLength = max(len(x) for x in lst )

    return maxList, maxLength

# Driver Code
lst = [['A'], ['A', 'B'], ['A', 'B', 'C']]
print(FindMaxLength(lst))
```

**Output:**

```py
(['A', 'B', 'C'], 3)

```

**方法 2 :** 使用`map`
在这个方法中，我们使用 Python 映射函数迭代内部列表来创建长度列表，然后使用 max 函数获得最大值。

```py
# Python3 program to Find maximum 
# length list in a nested list

def FindMaxLength(lst):
    maxList = max(lst, key = len)
    maxLength = max(map(len, lst))

    return maxList, maxLength

# Driver Code
lst = [['A'], ['A', 'B'], ['A', 'B', 'C'], ]
print(FindMaxLength(lst))
```

**Output:**

```py
(['A', 'B', 'C'], 3)

```

**方法#3 :** 使用`lambda` 运算符
Python 中查找最长长度列表的另一种方法是 lambda 运算符。它用于在 Python 中创建小型、一次性和匿名的函数对象。这里我们传递一个变量 *i* 作为 *len(i)* 表达式中的参数，并找到最大长度。

```py
# Python3 program to Find maximum 
# length list in a nested list

def FindMaxLength(lst):
    maxList = max(lst, key = lambda i: len(i))
    maxLength = len(maxList)

    return maxList, maxLength
# Driver Code
lst = [['A'], ['A', 'B'], ['A', 'B', 'C']]
print(FindMaxLength(lst))
```

**Output:**

```py
(['A', 'B', 'C'], 3)

```