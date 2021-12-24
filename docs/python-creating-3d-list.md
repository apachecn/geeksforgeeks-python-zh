# Python |创建 3D 列表

> 原文:[https://www.geeksforgeeks.org/python-creating-3d-list/](https://www.geeksforgeeks.org/python-creating-3d-list/)

三维列表意味着我们需要制作一个有三个参数的列表，即(a x b x c)，就像其他语言中的三维数组一样。在这个程序中，我们将尝试形成一个内容为“#”的三维列表。让我们看看下面这些例子:

```py
Input : 
3 x 3 x 3
Output :
[[['#', '#', '#'], ['#', '#', '#'], ['#', '#', '#']],
 [['#', '#', '#'], ['#', '#', '#'], ['#', '#', '#']],
 [['#', '#', '#'], ['#', '#', '#'], ['#', '#', '#']]]

Input :
5 x 3 x 2
Output :
[[['#', '#', '#', '#', '#'],
  ['#', '#', '#', '#', '#'],
  ['#', '#', '#', '#', '#']],
 [['#', '#', '#', '#', '#'],
  ['#', '#', '#', '#', '#'],
  ['#', '#', '#', '#', '#']]]

```

```py
# Python program to print 3D list
# importing pretty printed
import pprint

def ThreeD(a, b, c):
    lst = [[ ['#' for col in range(a)] for col in range(b)] for row in range(c)]
    return lst

# Driver Code
col1 = 5
col2 = 3
row = 2
# used the pretty printed function
pprint.pprint(ThreeD(col1, col2, row))
```

输出:

```py
[[['#', '#', '#', '#', '#'],
  ['#', '#', '#', '#', '#'],
  ['#', '#', '#', '#', '#']],
 [['#', '#', '#', '#', '#'],
  ['#', '#', '#', '#', '#'],
  ['#', '#', '#', '#', '#']]]

```

请参考 [pprint()](https://www.geeksforgeeks.org/pprint-data-pretty-printer-python/) 了解更多关于此主题的信息。

现在假设我们需要将两个 3D 列表合并成一个。

```py
# Python program to merge two 3D list into one
# importing pretty printed
import pprint

def ThreeD(a, b, c):
    lst1 = [[ ['1' for col in range(a)] for col in range(b)] for row in range(c)]
    lst2= [[ ['2' for col in range(a)] for col in range(b)] for row in range(c)]
    # Merging using "+" operator
    lst = lst1+lst2
    return lst

# Driver Code
col1 = 3
col2 = 3
row = 3

# used the pretty printed function
pprint.pprint(ThreeD(col1, col2, row))
```

输出:

```py
[[['1', '1', '1'], ['1', '1', '1'], ['1', '1', '1']],
 [['1', '1', '1'], ['1', '1', '1'], ['1', '1', '1']],
 [['1', '1', '1'], ['1', '1', '1'], ['1', '1', '1']],
 [['2', '2', '2'], ['2', '2', '2'], ['2', '2', '2']],
 [['2', '2', '2'], ['2', '2', '2'], ['2', '2', '2']],
 [['2', '2', '2'], ['2', '2', '2'], ['2', '2', '2']]]

```