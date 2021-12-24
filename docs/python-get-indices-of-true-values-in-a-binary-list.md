# Python |获取二进制列表中真值的索引

> 原文:[https://www . geesforgeks . org/python-get-indexs-of-true-values-in-a-binary-list/](https://www.geeksforgeeks.org/python-get-indices-of-true-values-in-a-binary-list/)

开发人员经常使用布尔列表在散列过程中检查真值。布尔列表也用于动态编程中的某些动态编程范例。让我们讨论在 Python 中获取列表中真值索引的某些方法。

**方法一:使用`enumerate()`和列表理解**

`enumerate()`可以用它的值做散列索引的任务，加上列表理解可以让我们检查真实值。

```py
# Python3 code to demonstrate 
# to return true value indices.
# using enumerate() + list comprehension

# initializing list 
test_list = [True, False, True, False, True, True, False]

# printing original list 
print ("The original list is : " +  str(test_list))

# using enumerate() + list comprehension
# to return true indices.
res = [i for i, val in enumerate(test_list) if val]

# printing result
print ("The list indices having True values are : " +  str(res))
```

**Output:**

```py
The original list is : [True, False, True, False, True, True, False]
The list indices having True values are : [0, 2, 4, 5]

```

**方法 2:使用`lambda + filter() + range()`**

`filter()`与 lambda 耦合的函数可以借助 range 函数执行该任务。`range()`功能用于遍历整个列表并过滤检查真实值。

```py
# Python3 code to demonstrate 
# to return true value indices.
# using lambda + filter() + range()

# initializing list 
test_list = [True, False, True, False, True, True, False]

# printing original list 
print ("The original list is : " +  str(test_list))

# using lambda + filter() + range()
# to return true indices.
res = list(filter(lambda i: test_list[i], range(len(test_list))))

# printing result
print ("The list indices having True values are : " +  str(res))
```

**Output:**

```py
The original list is : [True, False, True, False, True, True, False]
The list indices having True values are :  [0, 2, 4, 5]

```

**方法三:使用`itertools.compress()`**

`compress` 函数检查列表中的所有元素，并返回具有真值的索引列表。这是完成这一特殊任务的最简洁、最优雅的方式。

```py
# Python3 code to demonstrate 
# to return true value indices.
# using itertools.compress()
from itertools import compress

# initializing list 
test_list = [True, False, True, False, True, True, False]

# printing original list 
print ("The original list is : " +  str(test_list))

# using itertools.compress()
# to return true indices.
res = list(compress(range(len(test_list)), test_list))

# printing result
print ("The list indices having True values are : " +  str(res))
```

**Output:**

```py
The original list is : [True, False, True, False, True, True, False]
The list indices having True values are : [0, 2, 4, 5]

```