# Python–寻找多个集合的并集

> 原文:[https://www . geesforgeks . org/python-find-多集并集/](https://www.geeksforgeeks.org/python-find-union-of-multiple-sets/)

给定多个集合列表，任务是编写一个 Python 程序来寻找每个集合的并集。

**示例:**

> **输入:** test_list = [{4，3，5，2}，{8，4，7，2}，{1，2，3，4}，{9，5，3，7}]
> 
> **输出:** {1，2，3，4，5，7，8，9}
> 
> **说明:**包含所有集合的所有元素。已删除重复项。
> 
> **输入:** test_list = [{4，3，5，2}，{8，4，7，2}，{1，2，3，4}]
> 
> **输出:** {1，2，3，4，5，7，8}
> 
> **说明:**包含所有集合的所有元素。已删除重复项。

**方法#1:使用** [**联()**](https://www.geeksforgeeks.org/union-function-python/) **+ *符**

在本例中，我们使用 union()执行获取并集的任务，使用*运算符执行将所有集合打包在一起的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Union multiple sets
# Using union() + * operator

# initializing list
test_list = [{4, 3, 5, 2}, {8, 4, 7, 2}, {1, 2, 3, 4}, {9, 5, 3, 7}]

# printing original list
print("The original list is : " + str(test_list))

# * operator packs sets for union
res = set().union(*test_list)

# printing result
print("Multiple set union : " + str(res))
```

**输出:**

> 原始列表为:[{2，3，4，5}，{8，2，4，7}，{1，2，3，4}，{9，3，5，7}]
> 
> 多集并集:{1，2，3，4，5，7，8，9}

**方法 2:使用** [**链. from_iterable()**](https://www.geeksforgeeks.org/python-itertools-chain-from_iterable/) **+ *运算符**

在本例中，我们执行 union 任务，该任务又使用 from_iterable()进行展平。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Union multiple sets
# Using chain.from_iterable() + * operator
from itertools import chain

# initializing list
test_list = [{4, 3, 5, 2}, {8, 4, 7, 2}, {1, 2, 3, 4}, {9, 5, 3, 7}]

# printing original list
print("The original list is : " + str(test_list))

# * operator packs sets for union
res = set(chain(*test_list))

# printing result
print("Multiple set union : " + str(res))
```

**输出:**

> 原始列表为:[{2，3，4，5}，{8，2，4，7}，{1，2，3，4}，{9，3，5，7}]
> 
> 多集并集:{1，2，3，4，5，7，8，9}