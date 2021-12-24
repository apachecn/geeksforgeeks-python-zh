# Python–将列表与其他列表元素结合起来

> 原文:[https://www . geeksforgeeks . org/python-将列表与其他列表元素相结合/](https://www.geeksforgeeks.org/python-combine-list-with-other-list-elements/)

给定两个列表，将列表与另一个列表的每个元素组合在一起。

**示例:**

> **输入** : test_list = [3，5，7]，pair_list = ['Gfg '，' is '，' best']
> **输出** : [([3，5，7]，' Gfg ')，([3，5，7]，' is ')，([3，5，7]，' best')]
> **解释**:所有列表与其他列表中的每个元素配对。
> 
> **输入** : test_list = [3，5，7]，pair_list = ['Gfg '，' best']
> **输出** : [([3，5，7]，' Gfg ')，([3，5，7]，' best')]
> **解释**:与其他列表中每个元素配对的所有列表。

**方法#1:使用**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)**+**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+list()**

在本文中，我们使用 zip()将每个元素与使用 len()的其他列表的所有元素配对，并一次拾取每个元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Combine list with other list elements
# Using zip() + len() + list()

# initializing list
test_list = [3, 5, 7, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing pair list 
pair_list = ['Gfg', 'is', 'best']

# using zip() to pair element with pair list size
res = list(zip([test_list] * len(pair_list), pair_list))

# printing result 
print("The paired list : " + str(res))
```

**输出:**

> 原列表为:[3，5，7，9]
> 配对列表:[([3，5，7，9]，' Gfg ')，([3，5，7，9]，' is ')，([3，5，7，9]，' best')]

**方法 2:使用** [**品()**](https://www.geeksforgeeks.org/python-itertools-product/)

在本文中，我们使用 product()对元素进行配对，并将每个列表与配对列表中的每个元素进行映射。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Combine list with other list elements
# Using product()
from itertools import product

# initializing list
test_list = [3, 5, 7, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing pair list 
pair_list = ['Gfg', 'is', 'best']

# product() performs pairing of elements
res = list(product([test_list], pair_list))

# printing result 
print("The paired list : " + str(res))
```

**输出:**

> 原列表为:[3，5，7，9]
> 配对列表:[([3，5，7，9]，' Gfg ')，([3，5，7，9]，' is ')，([3，5，7，9]，' best')]