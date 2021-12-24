# Python |检查元组的元组中是否存在元素

> 原文:[https://www . geesforgeks . org/python-检查元组元组中是否存在元素/](https://www.geeksforgeeks.org/python-check-if-element-is-present-in-tuple-of-tuples/)

有时我们使用的数据是元组形式的，通常我们也需要查看嵌套元组。这可以解决的常见问题是在数据预处理中寻找丢失的数据或 N.A 值。让我们讨论一下实现这一点的某些方法。

**方法一:使用`any()`**
`any` 功能执行此任务。它只是逐个测试元素是否作为元组元素存在。如果元素存在，则返回 true，否则返回 false。

```py
# Python3 code to demonstrate 
# test for values in tuple of tuple
# using any()

# initializing tuple of tuple 
test_tuple = (("geeksforgeeks", "gfg"), ("CS_Portal", "best"))

# printing tuple
print ("The original tuple is " + str(test_tuple))

# using any()
# to test for value in tuple of tuple
if (any('geeksforgeeks' in i for i in test_tuple)) :
    print("geeksforgeeks is present")
else :
    print("geeksforgeeks is not present")
```

**输出:**

```py
The original tuple is (('geeksforgeeks', 'gfg'), ('CS_Portal', 'best'))
geeksforgeeks is present

```

**方法 2:使用`itertools.chain()`**
`chain` 函数测试所有中间元组的期望值，然后如果在搜索的任何元组中存在所需值，则返回真。

```py
# Python3 code to demonstrate 
# test for values in tuple of tuple
# using itertools.chain()
import itertools

# initializing tuple of tuple 
test_tuple = (("geeksforgeeks", "gfg"), ("CS_Portal", "best"))

# printing tuple
print ("The original tuple is " + str(test_tuple))

# using itertools.chain()
# to test for value in tuple of tuple
if ('geeksforgeeks' in itertools.chain(*test_tuple)) :
    print("geeksforgeeks is present")
else :
    print("geeksforgeeks is not present")
```

**输出:**

```py
The original tuple is (('geeksforgeeks', 'gfg'), ('CS_Portal', 'best'))
geeksforgeeks is present

```