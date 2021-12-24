# Python–itertools . aggregate()

> 原文:[https://www.geeksforgeeks.org/python-itertools-accumulate/](https://www.geeksforgeeks.org/python-itertools-accumulate/)

[Python itertools](https://www.geeksforgeeks.org/python-itertools/#combine) 模块是处理迭代器的工具集合。

**根据官方文件:**

> “模块[它]实现了许多迭代器构建块，灵感来自 APL、Haskell 和 SML 的构造……它们共同构成了一个‘迭代器代数’，使得用纯 Python 简洁高效地构造专用工具成为可能。”这基本上意味着 itertools 中的函数对迭代器进行“操作”以产生更复杂的迭代器。

简单地说，迭代器是可以在 for 循环中使用的数据类型。Python 中最常见的迭代器是列表。

让我们创建一个字符串列表，并将其命名为颜色。我们可以使用 for 循环来迭代列表，如下所示:

```py
colors = ['red', 'orange', 'yellow', 'green']

# Iterating List
for each in colors:
    print(each)
```

**Output:**

```py
red
orange
yellow
green

```

有许多不同种类的列表，但是现在，我们将使用列表和集合。

**使用 itertools 的要求**

使用前必须导入 **itertools** 模块。我们还必须导入**操作员**模块，因为我们想与操作员一起工作。

```py
import itertools
import operator ## only needed if want to play with operators
```

**Itertools** 模块是函数的集合。我们将探索其中一个**累加()**函数。

**注:**更多信息请参考 [Python Itertools](https://www.geeksforgeeks.org/python-itertools/#combine)

## 累积()

这个迭代器接受两个参数，可迭代目标和在目标值的每次迭代中要遵循的函数。如果没有传递函数，默认情况下会发生加法。如果输入表为空，输出表也将为空。

> **语法**
> ITER tools . aggregate(可迭代[，func])—>累加对象

这个函数生成一个迭代器，返回函数的结果。

**参数**
可迭代&功能

现在理论部分已经讲够了，让我们来玩代码

**代码:1**

```py
# import the itertool module 
# to work with it
import itertools

# import operator to work 
# with operator
import operator

# creating a list GFG
GFG = [1, 2, 3, 4, 5]

# using the itertools.accumulate() 
result = itertools.accumulate(GFG, 
                              operator.mul)

# printing each item from list
for each in result:
    print(each)
```

**Output:**

```py
1
2
6
24
120

```

**说明:**

运算符. mul 取两个数字并相乘。

```py
operator.mul(1, 2)
2
operator.mul(2, 3)
6
operator.mul(6, 4)
24
operator.mul(24, 5)
120

```

现在在下一个例子中，我们将使用 max 函数，因为它也将一个函数作为参数。

**代码 2:**

```py
# import the itertool module 
# to work with it
import itertools

# import operator to work with
# operator
import operator

# creating a list GFG
GFG = [5, 3, 6, 2, 1, 9, 1]

# using the itertools.accumulate()

# Now here no need to import operator
# as we are not using any operator
# Try after removing it gives same result
result = itertools.accumulate(GFG, max)

# printing each item from list
for each in result:
    print(each)
```

**Output:**

```py
5
5
6
6
6
9
9

```

**说明:**

```py
5
max(5, 3)
5
max(5, 6)
6
max(6, 2)
6
max(6, 1)
6
max(6, 9)
9
max(9, 1)
9
```

**注意:**传递函数是可选的，就好像你不会传递一样，默认情况下，任何函数项都会被求和即相加。

**ITER tools . aggregate(set . difference)**
此返回集合间差异项目的累积。

**代码解释**

```py
# import the itertool module to
# work with it
import itertools

# creating a set GFG1 and GFG2
GFG1 = { 5, 3, 6, 2, 1, 9 }
GFG2 ={ 4, 2, 6, 0, 7 }

# using the itertools.accumulate()

# Now this will first give difference 
# and the give result by adding all 
# the element in result as by default
# if no function  passed it will add always
result = itertools.accumulate(GFG2.difference(GFG1))

# printing each item from list
for each in result:
    print(each)
```

**Output:**

```py
0
4
11

```