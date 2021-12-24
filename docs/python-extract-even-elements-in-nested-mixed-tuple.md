# Python–提取嵌套混合元组中的偶数元素

> 原文:[https://www . geesforgeks . org/python-extract-偶数元素嵌套-混合元组/](https://www.geeksforgeeks.org/python-extract-even-elements-in-nested-mixed-tuple/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要从元组中获取所有偶数元素。元组可以嵌套或混合。这种问题可能发生在数据域中。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = (5，(7，6，(2，(4)、(5)))
> 输出 : ((6，(2，(4)、(5)))，)
> 
> **输入** : test_tuple = (5，(8，6，(2，(4，8))))
> **输出** : ((8，6，(2，(4，8)))，)

**方法#1:使用递归+ isinstance() + loop**
这是执行这个任务的方法之一。在本例中，我们使用 isinstance()执行将元素实例设置为整数的任务，一旦遇到元组，函数就会递归。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract Even elements in Nested Mixed Tuple
# Using recursion + isinstance() + loop

# helper_fnc
def even_ele(test_tuple, even_fnc):
    res = tuple()
    for ele in test_tuple:
        if isinstance(ele, tuple):
            res += (even_ele(ele, even_fnc), )
        elif even_fnc(ele):
            res += (ele, )
    return res

# initializing tuples
test_tuple = (4, 5, (7, 6, (2, 4)), 6, 8)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Extract Even elements in Nested Mixed Tuple
# Using recursion + isinstance() + loop
res = even_ele(test_tuple, lambda x: x % 2 == 0)

# printing result
print("Even elements of tuple : " + str(res))
```

**Output : **

```py
The original tuple : (4, 5, (7, 6, (2, 4)), 6, 8)
Even elements of tuple : (4, (6, (2, 4)), 6, 8)
```

**方法 2:使用递归+ isinstance() +生成器表达式**
该方法以与上述方法类似的方式执行该任务。不同的只是它是上述方法的简写，使用生成器表达式在一行中完成工作。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Extract Even elements in Nested Mixed Tuple
# Using recursion + isinstance() + generator expression

# helper_fnc
def even_ele(test_tuple, even_fnc):
    return tuple(even_ele(ele, even_fnc) if isinstance(ele, tuple) else ele
    for ele in test_tuple if isinstance(ele, tuple) or even_fnc(ele))

# initializing tuples
test_tuple = (4, 5, (7, 6, (2, 4)), 6, 8)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Extract Even elements in Nested Mixed Tuple
# Using recursion + isinstance() + generator expression
res = even_ele(test_tuple, lambda x: x % 2 == 0)

# printing result
print("Even elements of tuple : " + str(res))
```

**Output : **

```py
The original tuple : (4, 5, (7, 6, (2, 4)), 6, 8)
Even elements of tuple : (4, (6, (2, 4)), 6, 8)
```