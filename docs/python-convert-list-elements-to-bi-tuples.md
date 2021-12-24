# Python |将列表元素转换为二元组

> 原文:[https://www . geesforgeks . org/python-convert-list-elements-to-bi-tuples/](https://www.geeksforgeeks.org/python-convert-list-elements-to-bi-tuples/)

有时候，在使用 Python 列表时，我们可能会遇到一个子问题，在这个子问题中，我们需要将一个特定的元素与每个列表元素联系起来。当使用查询和过滤器时，这个任务可以在 web 开发领域中使用。让我们讨论一下解决这个问题的方法。

**方法:使用`zip() + repeat()`**

这个问题可以使用`zip()`来解决，该`zip()`可以使用`repeat()`来附加到每个具有确定编号的列表元素。

```py
# Python3 code to demonstrate working of
# Convert list elements to bi-tuples
# using zip() + repeat()
from itertools import repeat

# initialize list
test_list = [5, 6, 7, 8, 4, 3]

# printing original list
print("The original list is : " + str(test_list))

# initialize attach element
ele = 'gfg'

# Convert list elements to bi-tuples
# using zip() + repeat()
res = list(zip(test_list, repeat(ele)))

# printing result
print("Tuple list after attaching element : " + str(res))
```

**Output :**

> 原列表为:【5，6，7，8，4，3】
> 附加元素后的元组列表:[(5，' gfg ')，(6，' gfg ')，(7，' gfg ')，(8，' gfg ')，(4，' gfg ')，(3，' gfg')]

**方法 2:使用`map()`+λ**
这是可以执行该任务的另一种方式。在本文中，我们只是使用 map()将向列表元素添加元素的逻辑扩展到所有元素，方法是为它提供 lambda 函数来执行计算任务。

```py
# Python3 code to demonstrate working of
# Convert list elements to bi-tuples
# using map() + lambda
from itertools import repeat

# initialize list
test_list = [5, 6, 7, 8, 4, 3]

# printing original list
print("The original list is : " + str(test_list))

# initialize attach element
ele = 'gfg'

# Convert list elements to bi-tuples
# using map() + lambda
res = list(map(lambda key : (key, ele), test_list))

# printing result
print("Tuple list after attaching element : " + str(res))
```

**Output :**

> 原列表为:【5，6，7，8，4，3】
> 附加元素后的元组列表:[(5，' gfg ')，(6，' gfg ')，(7，' gfg ')，(8，' gfg ')，(4，' gfg ')，(3，' gfg')]