# Python |将元组列表转换为数字

> 原文:[https://www . geeksforgeeks . org/python-将元组列表转换为数字/](https://www.geeksforgeeks.org/python-convert-list-of-tuples-into-digits/)

给定一个元组列表，任务是将其转换为列表元素中存在的所有数字的列表。

让我们讨论执行这项任务的某些方式。

**方法#1:使用`re`**

将元组列表转换为列表元素中存在的所有数字的列表，最简洁易读的方法是使用 *re* 。

```
# Python code to convert list of tuples into
# list of all digits which exists
# in elements of list.

# Importing
import re

# Input list initialization
lst = [(11, 100), (22, 200), (33, 300), (44, 400), (88, 800)]

# Using re
temp = re.sub(r'[\[\]\(\), ]', '', str(lst))

# Using set
Output = [int(i) for i in set(temp)]

# Printing output
print("Initial List is :", lst)
print("Output list is :", Output)
```

**Output:**

> 初始列表为:[(11，100)，(22，200)，(33，300)，(44，400)，(88，800)]
> 输出列表为:[1，4，8，0，3，2]

**方法二:使用`itertools.chain()``lambda()`**

这是使用`lambda()`执行该特定任务的另一种方式。

```
# Python code to convert list of tuples into
# list of all digits which exists
# in elements of list.

# Importing
from itertools import chain

# Input list initialization
lst = [(11, 100), (22, 200), (33, 300), (44, 400), (88, 800)]

# using lambda
temp = map(lambda x: str(x), chain.from_iterable(lst))

# Output list initialization
Output = set()

# Adding element in Output
for x in temp:
    for elem in x:
        Output.add(elem)

# Printing output
print("Initial List is :", lst)
print("Output list is :", Output)
```

**Output:**

> 初始列表为:[(11，100)，(22，200)，(33，300)，(44，400)，(88，800)]
> 输出列表为:{'8 '，' 4 '，' 0 '，' 2 '，' 1 '，' 3'}