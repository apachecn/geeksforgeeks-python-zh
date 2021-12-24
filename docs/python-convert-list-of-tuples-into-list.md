# Python |将元组列表转换为列表

> 原文:[https://www . geesforgeks . org/python-convert-list-of-tuples-to-list/](https://www.geeksforgeeks.org/python-convert-list-of-tuples-into-list/)

给定一个元组列表，编写一个 Python 程序将其转换为列表。

**示例:**

```
Input: [(11, 20), (13, 40), (55, 16)]
Output:[11, 20, 13, 40, 55, 16]

Input: [('Geeks', 2), ('For', 4), ('geek', '6')]
Output: ['Geeks', 2, 'For', 4, 'geek', '6']

```

下面是将元组列表转换为列表的方法。

**方法#1 :** 使用列表理解

```
# Python code to convert list of tuples into list

# List of tuple initialization
lt = [('Geeks', 2), ('For', 4), ('geek', '6')]

# using list comprehension
out = [item for t in lt for item in t]

# printing output
print(out)
```

**Output:**

```
['Geeks', 2, 'For', 4, 'geek', '6']

```

**方法 2 :** 使用 itertools

```
# Python code to convert list of tuple into list

# Importing
import itertools

# List of tuple initialization
tuple = [(1, 2), (3, 4), (5, 6)]

# Using itertools
out = list(itertools.chain(*tuple))

# printing output
print(out)
```

**Output:**

```
[1, 2, 3, 4, 5, 6]

```

**方法#3 :** 使用迭代

```
# Python code to convert list of tuple into list

# List of tuple initialization
tup = [(1, 2), (3, 4), (5, 6)]

# result list initialization
result = []

for t in tup:
    for x in t:
        result.append(x)

# printing output
print(result)
```

**Output:**

```
[1, 2, 3, 4, 5, 6]

```

**方法#4 :** 使用`sum`

```
# Python code to convert list of tuple into list

# List of tuple initialization
tup = [(1, 2), (3, 4), (5, 6)]

# using sum function()
out = list(sum(tup, ()))

# printing output
print(out)
```

**Output:**

```
[1, 2, 3, 4, 5, 6]

```

**方法 5 :** 使用**运算符**和**减少**

```
# Python code to convert list of tuple into list

import operator
from functools import reduce

# List of tuple initialization
tup = [(1, 2), (3, 4), (5, 6)]

# printing output
print(list(reduce(operator.concat, tup)))
```

**Output:**

```
[1, 2, 3, 4, 5, 6]

```

**方法 6 :** 使用`lambda`

```
# Python code to convert list of tuple into list

# List of tuple initialization
tup = [(1, 2), (3, 4), (5, 6)]

# Using map for 0 index
b = map(lambda x: x[0], tup)

# Using map for 1 index
c = map(lambda x: x[1], tup)

# converting to list
b = list(b)
c = list(c)

# Combining output
out = b + c

# printing output
print(out)
```

**Output:**

```
[1, 3, 5, 2, 4, 6]

```