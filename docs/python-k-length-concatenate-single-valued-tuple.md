# Python–K 长度连接单值元组

> 原文:[https://www . geesforgeks . org/python-k-length-concatenate-单值-tuple/](https://www.geeksforgeeks.org/python-k-length-concatenate-single-valued-tuple/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要执行单值元组的串联，以使它们成为更大的组。这种问题可能发生在网页开发和日常编程中。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [(3、、(6)、(8)、(2)、(9)、(4)、(7)、(1)、(8)】、K = 4
> **输出** : [(3、6、8、2)、(9、4、7、1)】
> **输入** : test_list = [(3、、(6)、(8)、(2)、(9)、(4)、(7)、(1)】、K

**方法#1:使用 zip() +列表理解**
以上功能的组合可以用来解决这个问题。在本文中，我们使用 zip()来完成分组任务，并使用列表理解来构建值。K 的大小只能限制在 2。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# K length Concatenate Single Valued Tuple
# Using zip() + list comprehension

# initializing lists
test_list = [(3, ), (6, ), (8, ), (2, ), (9, ), (4, )]

# printing original list
print("The original list is : " + str(test_list))

# K length Concatenate Single Valued Tuple
# Using zip() + list comprehension
res = [a + b for a, b in zip(test_list[::2], test_list[1::2])]

# printing result
print("Concatenated tuples : " + str(res))
```

**Output : **

```
The original list is : [(3, ), (6, ), (8, ), (2, ), (9, ), (4, )]
Concatenated tuples : [(3, 6), (8, 2), (9, 4)]
```

**方法 2:使用 zip _ long()+chain . from _ iterables()**
以上函数的组合可以用来解决这个问题。在本文中，我们使用 zip _ longest()执行连接任务，并且使用 chain.from_iterables()在连接之前将元组展平为列表元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# K length Concatenate Single Valued Tuple
# Using zip_longest() + chain.from_iterables()
from itertools import chain, zip_longest

# initializing lists
test_list = [(3, ), (6, ), (8, ), (2, ), (9, ), (4, )]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 3

# K length Concatenate Single Valued Tuple
# Using zip() + list comprehension
temp = [iter(chain.from_iterable(test_list))] * K
res = list(zip_longest(*temp))

# printing result
print("Concatenated tuples : " + str(res))
```

**Output : **

```
The original list is : [(3, ), (6, ), (8, ), (2, ), (9, ), (4, )]
Concatenated tuples : [(3, 6, 8), (2, 9, 4)]
```