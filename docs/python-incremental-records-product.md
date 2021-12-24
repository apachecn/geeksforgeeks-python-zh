# Python |增量记录产品

> 原文:[https://www . geesforgeks . org/python-增量-记录-产品/](https://www.geeksforgeeks.org/python-incremental-records-product/)

有时，在处理数据时，我们会遇到一个问题，即我们需要找到元组中每个索引的累积积。这个问题可以应用于 web 开发和竞争性编程领域。让我们讨论一下解决这个问题的某些方法。

**方法:使用`accumulate()` + loop + `lambda + map() + tuple() + zip()`**
以上功能的组合可以用来解决这个任务。在本例中，我们使用 zip()对元素进行配对，然后执行它们的乘积，并使用 map()将其扩展到所有元素。产品的推进是通过使用累加来完成的。所有逻辑的绑定都是由 lambda 函数完成的。

```py
# Python3 code to demonstrate working of
# Incremental Records Product
# Using accumulate() + loop + lambda + map() + tuple() + zip()
from itertools import accumulate

def prod(val) :     
    res = 1         
    for ele in val:         
        res *= ele         
    return res

# initialize list
test_list = [(3, 4, 5), (4, 5, 7), (1, 4, 10)]

# printing original list 
print("The original list : " + str(test_list))

# Incremental Records Product
# Using accumulate() + loop + lambda + map() + tuple() + zip()
res = list(accumulate(test_list, lambda i, j: tuple(map(prod, zip(i, j)))))

# printing result
print("Accumulative index product of tuple list : " + str(res))
```

**Output :**

```py
The original list : [(3, 4, 5), (4, 5, 7), (1, 4, 10)]
Accumulative index product of tuple list : [(3, 4, 5), (12, 20, 35), (12, 80, 350)]

```