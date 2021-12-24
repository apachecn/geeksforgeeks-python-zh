# Python |所有可能的 N 个组合元组

> 原文:[https://www . geeksforgeeks . org/python-全可能-n-组合-元组/](https://www.geeksforgeeks.org/python-all-possible-n-combination-tuples/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要生成所有可能的组合对，直到 n。这可能在数学领域有应用。让我们讨论一下解决这个问题的某些方法。
**方法#1:使用列表理解+乘积()**
这个任务可以使用列表理解来执行，列表理解可以用来迭代 N 个数字的容器，乘积()执行从它们形成组合的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# All possible N combination tuples
# Using list comprehension + product()
from itertools import product

# initialize N
N = 3

# All possible N combination tuples
# Using list comprehension + product()
res = [ele for ele in product(range(1, N + 1), repeat = N)]

# printing result
print("Tuple Combinations till N are : " + str(res))
```

**Output : **

元组组合直到 N 为:[(1，1，1)，(1，1，2)，(1，1，3)，(1，2，1)，(1，2，2)，(1，2，3)，(1，3，1)，(1，3，2)，(1，3，3)，(2，1，1)，(2，1，2，(2，1，3)，(2，2，1)，(2，2，1)，(2，2，2，2)，(2，3)，(2，3，1)，(2，3，1)，(2，3，2，(2，3，3，2)，(3，1，1)，(3，1，1，3，1，1)

**方法#2:使用 product()**
这个任务也可以只使用单一功能来执行。使用转换为列表可以消除列表理解的使用。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# All possible N combination tuples
# Using product()
from itertools import product

# initialize N
N = 3

# All possible N combination tuples
# Using product()
res = list(product(range(1, N + 1), repeat = N))

# printing result
print("Tuple Combinations till N are : " + str(res))
```

**Output : **

元组组合直到 N 为:[(1，1，1)，(1，1，2)，(1，1，3)，(1，2，1)，(1，2，2)，(1，2，3)，(1，3，1)，(1，3，2)，(1，3，3)，(2，1，1)，(2，1，2，(2，1，3)，(2，2，1)，(2，2，1)，(2，2，2，2)，(2，3)，(2，3，1)，(2，3，1)，(2，3，2，(2，3，3，2)，(3，1，1)，(3，1，1，3，1，1)