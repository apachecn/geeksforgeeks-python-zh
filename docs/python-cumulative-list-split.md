# Python–累计列表拆分

> 原文:[https://www.geeksforgeeks.org/python-cumulative-list-split/](https://www.geeksforgeeks.org/python-cumulative-list-split/)

有时，在处理字符串列表时，我们可能会遇到一个问题，即我们需要执行拆分任务，并以累积的方式返回列表的所有拆分实例。这种问题可能发生在涉及数据的许多领域。让我们讨论执行这项任务的某些方法。
**方法#1:使用循环**
这是执行这个任务的蛮力方式。在本例中，我们测试列表，并在遇到拆分字符时追加列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Cumulative List Split
# Using loop

# initializing list
test_list = ['gfg-is-all-best']

# printing original list
print("The original list is : " + str(test_list))

# initializing Split char
spl_char = "-"

# Cumulative List Split
# Using loop
res = []
for sub in test_list:
    for idx in range(len(sub)):
        if sub[idx] == spl_char:
            res.append([ sub[:idx] ])
    res.append([ sub ])

# printing result
print("The Cumulative List Splits : " + str(res))
```

**Output**

```py
The original list is : ['gfg-is-all-best']
The Cumulative List Splits : [['gfg'], ['gfg-is'], ['gfg-is-all'], ['gfg-is-all-best']]

```

**方法 2:使用累加()+ join()**
这是解决这个问题的一种线性方法。在这种情况下，我们执行切入累积的任务，使用累加和连接()来构造结果列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Cumulative List Split
# Using accumulate() + join()
from itertools import accumulate

# initializing list
test_list = ['gfg-is-all-best']

# printing original list
print("The original list is : " + str(test_list))

# initializing Split char
spl_char = "-"

# Cumulative List Split
# Using accumulate() + join()
temp = test_list[0].split(spl_char)
res = list(accumulate(temp, lambda x, y: spl_char.join([x, y])))

# printing result
print("The Cumulative List Splits : " + str(res))
```

**Output**

```py
The original list is : ['gfg-is-all-best']
The Cumulative List Splits : ['gfg', 'gfg-is', 'gfg-is-all', 'gfg-is-all-best']

```