# Python |比较元组

> 原文:[https://www.geeksforgeeks.org/python-compare-tuples/](https://www.geeksforgeeks.org/python-compare-tuples/)

有时，在处理记录时，我们会遇到一个问题，即我们需要检查一个元组的每个元素是否大于/小于它在其他元组中的对应索引。这可能有许多可能的应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`all() + generator expression + zip()`**
上述功能的组合可用于执行该任务。在这里，我们只是使用`all()`比较所有元素。交叉元组访问由`zip()`完成，生成器表达式为我们提供了比较的逻辑。

```
# Python3 code to demonstrate working of
# Comparing tuples
# using generator expression + all() + zip()

# initialize tuples 
test_tup1 = (10, 4, 5)
test_tup2 = (13, 5, 18)

# printing original tuples 
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Comparing tuples
# using generator expression + all() + zip()
res = all(x < y for x, y in zip(test_tup1, test_tup2))

# printing result
print("Are all elements in second tuple greater than first ? : " + str(res))
```

**Output :**

```
The original tuple 1 : (10, 4, 5)
The original tuple 2 : (13, 5, 18)
Are all elements in second tuple greater than first ? : True

```