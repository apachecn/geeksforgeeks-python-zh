# Python |检查元组是否有任何无值

> 原文:[https://www . geesforgeks . org/python-check-if-tuple-any-none-value/](https://www.geeksforgeeks.org/python-check-if-tuple-has-any-none-value/)

有时，在使用 Python 时，我们可能会遇到一个问题，即我们有一条记录，我们需要检查它是否包含所有有效值，即是否有任何无值。这种问题在数据预处理步骤中很常见。让我们讨论执行这项任务的某些方法。

**方法#1:使用`any() + map() + lambda`**
结合以上功能可以执行此任务。在本例中，我们使用 any()检查任何元素，逻辑的扩展由 map()和 lambda 完成。

```
# Python3 code to demonstrate working of
# Check if tuple has any None value
# using any() + map() + lambda

# initialize tuple
test_tup = (10, 4, 5, 6, None)

# printing original tuple
print("The original tuple : " + str(test_tup))

# Check if tuple has any None value
# using any() + map() + lambda
res = any(map(lambda ele: ele is None, test_tup))

# printing result
print("Does tuple contain any None value ? : " + str(res))
```

**Output :**

```
The original tuple : (10, 4, 5, 6, None)
Does tuple contain any None value ? : True

```