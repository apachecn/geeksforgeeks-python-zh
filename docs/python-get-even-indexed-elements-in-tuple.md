# Python–获取元组中的偶数索引元素

> 原文:[https://www . geesforgeks . org/python-get-even-indexed-in-elements-tuple/](https://www.geeksforgeeks.org/python-get-even-indexed-elements-in-tuple/)

有时，在使用 Python 数据时，我们可能会遇到一个问题，我们需要执行提取元组中甚至索引元素的任务。这种问题很常见，可能会应用于许多领域，例如日常编程。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = (1，2，4，5，6)
> **输出** : (1，4，6)
> 
> **输入** : test_tuple = (1，2，4)
> 输出 : (1，4)

**方法#1:使用`tuple() + generator expression + enumerate()`**
以上功能的组合可以用来解决这个问题。在本文中，我们使用生成器表达式执行迭代任务，使用枚举()检查偶数索引，并使用元组()将结果转换为元组。

```py
# Python3 code to demonstrate working of 
# Extract Even indexed elements in Tuple
# Using tuple() + generator expression + enumerate()

# initializing tuples
test_tuple = (5, 'Gfg', 2, 8.8, 1.2, 'is')

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Extract Even indexed elements in Tuple
# Using tuple() + generator expression + enumerate()
res = tuple(ele for idx, ele in enumerate(test_tuple) if idx % 2 == 0)

# printing result 
print("The even indexed elements : " + str(res))
```

**Output :**

```py
The original tuple : (5, 'Gfg', 2, 8.8, 1.2, 'is')
The even indexed elements : (5, 2, 1.2)

```

**方法#2:使用递归**
这是执行该任务的另一种方式。在这种情况下，我们进入重现。函数新列表，提取初始元素，并再次传递列表，直到列表结束，只提取偶数索引元素。

```py
# Python3 code to demonstrate working of 
# Extract Even indexed elements in Tuple
# Using recursion

def helper_fnc(test_tuple):
    if len(test_tuple) == 0 or len(test_tuple) == 1:
        return ()
    return (test_tuple[0], ) + helper_fnc(test_tuple[2:])

# initializing tuples
test_tuple = (5, 'Gfg', 2, 8.8, 1.2, 'is')

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Extract Even indexed elements in Tuple
# Using recursion
res = helper_fnc(test_tuple)

# printing result 
print("The even indexed elements : " + str(res))
```

**Output :**

```py
The original tuple : (5, 'Gfg', 2, 8.8, 1.2, 'is')
The even indexed elements : (5, 2, 1.2)

```