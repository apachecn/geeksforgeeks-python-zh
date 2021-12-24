# Python–展平嵌套元组

> 原文:[https://www.geeksforgeeks.org/python-flatten-nested-tuples/](https://www.geeksforgeeks.org/python-flatten-nested-tuples/)

有时，在使用 Python 元组时，我们可能会遇到一个问题，即我们需要对元组执行扁平化，这可能是嵌套的，也可能是不希望的。这可以应用于许多领域，如数据科学和网络开发。让我们讨论一下执行这项任务的具体方法。

```
Input : test_tuple = ((4, 7), ((4, 5), ((6, 7), (7, 6))))
Output : ((4, 7), (4, 5), (6, 7), (7, 6))

Input : test_tuple = ((4, 7), (5, 7), (1, 3))
Output : ((4, 7), (5, 7), (1, 3))
```

**方法:使用递归+ isinstance()**
以上功能的结合可以帮助我们实现这个问题的解决。在这种情况下，我们使用递归来执行为内部元组挖掘每个元组的任务，对于扁平化的决策，isinstance()根据元组容器或原语数据来使用。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Flatten Nested Tuples
# Using recursion + isinstance()

# helper function
def flatten(test_tuple):

    if isinstance(test_tuple, tuple) and len(test_tuple) == 2 and not isinstance(test_tuple[0], tuple):
        res = [test_tuple]
        return tuple(res)

    res = []
    for sub in test_tuple:
        res += flatten(sub)
    return tuple(res)

# initializing tuple
test_tuple = ((4, 5), ((4, 7), (8, 9), (10, 11)), (((9, 10), (3, 4))))

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Flatten Nested Tuples
# Using recursion + isinstance()
res = flatten(test_tuple)

# printing result
print("The flattened tuple : " + str(res))
```

**Output : **

```
The original tuple : ((4, 5), ((4, 7), (8, 9), (10, 11)), ((9, 10), (3, 4)))
The flattened tuple : ((4, 5), (4, 7), (8, 9), (10, 11), (9, 10), (3, 4))
```