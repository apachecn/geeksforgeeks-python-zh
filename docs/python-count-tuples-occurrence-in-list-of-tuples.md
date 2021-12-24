# Python |统计元组列表中元组的出现次数

> 原文:[https://www . geesforgeks . org/python-计数-元组-元组列表中出现次数/](https://www.geeksforgeeks.org/python-count-tuples-occurrence-in-list-of-tuples/)

在用 Python 开发网络和桌面产品时，我们经常使用嵌套列表，并且有几个关于如何找到唯一元组计数的查询。让我们看看如何在给定的元组列表中获得唯一元组的计数。

以下是实现上述任务的一些方法。

**方法#1:** 使用迭代

```
# Python code to count unique 
# tuples in list of list

import collections 
Output = collections.defaultdict(int)

# List initialization
Input = [[('hi', 'bye')], [('Geeks', 'forGeeks')],
         [('a', 'b')], [('hi', 'bye')], [('a', 'b')]]

# Using iteration
for elem in Input:
      Output[elem[0]] += 1

# Printing output
print(Output)
```

**Output:**

```
defaultdict(<class 'int'>, {('Geeks', 'forGeeks'): 1, ('hi', 'bye'): 2, ('a', 'b'): 2})

```

**方法 2:使用`chain` 和`Counter`**

```
# Python code to count unique 
# tuples in list of list

# Importing
from collections import Counter
from itertools import chain

# List initialization
Input = [[('hi', 'bye')], [('Geeks', 'forGeeks')],
         [('a', 'b')], [('hi', 'bye')], [('a', 'b')]]

# Using counter and chain
Output = Counter(chain(*Input))

# Printing output
print(Output)
```

**Output:**

```
Counter({('hi', 'bye'): 2, ('a', 'b'): 2, ('Geeks', 'forGeeks'): 1})

```