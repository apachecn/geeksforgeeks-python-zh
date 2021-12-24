# Python |追加奇数元素两次

> 原文:[https://www . geesforgeks . org/python-append-odd-element-twice/](https://www.geeksforgeeks.org/python-append-odd-element-twice/)

给定一个数字列表，任务是从初始列表创建一个新列表，条件是每奇数个元素追加两次。

以下是实现上述任务的一些方法。

**方法一:使用列表理解**

```
# Python code to create a new list from initial list
# with condition to append every odd element twice.

# List initialization
Input = [1, 2, 3, 8, 9, 11]

# Using list comprehension 
Output = [elem for x in Input for elem in (x, )*(x % 2 + 1)]

# printing 
print("Initial list is:'", Input)
print("New list is:", Output)
```

**Output:**

```
Initial list is:' [1, 2, 3, 8, 9, 11]
New list is: [1, 1, 2, 3, 3, 8, 9, 9, 11, 11]

```

**方法 2:使用迭代工具**

```
# Python code to create a new list from initial list
# with condition to append every odd element twice.

# Importing
from itertools import chain

# List initialization
Input = [1, 2, 3, 8, 9, 11]

# Using list comprehension  and chain
Output = list(chain.from_iterable([i] 
              if i % 2 == 0 else [i]*2 for i in Input))

# printing 
print("Initial list is:'", Input)
print("New list is:", Output)
```

**Output:**

```
Initial list is:' [1, 2, 3, 8, 9, 11]
New list is: [1, 1, 2, 3, 3, 8, 9, 9, 11, 11]

```

**方法三:使用 Numpy 数组**

```
# Python code to create a new list from initial list
# with condition to append every odd element twice.

# Importing
import numpy as np

# List initialization
Input = [1, 2, 3, 8, 9, 11]
Output = []

# Using Numpy repeat
for x in Input:
    (Output.extend(np.repeat(x, 2, axis = 0))
      if x % 2 == 1 else Output.append(x))

# printing 
print("Initial list is:'", Input)
print("New list is:", Output)
```

**Output:**

```
Initial list is:' [1, 2, 3, 8, 9, 11]
New list is: [1, 1, 2, 3, 3, 8, 9, 9, 11, 11]

```