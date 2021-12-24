# Python |检查无元组

> 原文:[https://www.geeksforgeeks.org/python-check-for-none-tuple/](https://www.geeksforgeeks.org/python-check-for-none-tuple/)

有时，在处理 Python 记录时，我们可能会遇到一个问题，即我们需要过滤掉所有只包含无值的元组。这在数据科学领域有可能得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`all()` +生成器表达式**
上述功能的组合可用于执行该特定任务。在本文中，我们使用生成器表达式来提供无的逻辑，并且每个元素的检查由`all()`来处理。

```
# Python3 code to demonstrate working of
# Check for None Tuple
# using all() + generator expression

# initialize tuple
test_tup = (None, None, None, None, None)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Check for None Tuple
# using all() + generator expression
res = all(ele is None for ele in test_tup)

# printing result
print("Does tuple contain all None elements ? : " + str(res))
```

**Output :**

```
The original tuple : (None, None, None, None, None)
Does tuple contain all None elements ? : True

```