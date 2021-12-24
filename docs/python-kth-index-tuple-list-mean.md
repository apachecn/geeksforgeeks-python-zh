# Python–第 Kth 个索引元组列表平均值

> 原文:[https://www . geesforgeks . org/python-kth-index-tuple-list-mean/](https://www.geeksforgeeks.org/python-kth-index-tuple-list-mean/)

有时，在使用 Python 元组时，我们会遇到一个问题，即我们需要计算列表中任何特定元组索引的平均值。这种问题可以在数据领域如 web 开发中得到应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_list = [('Gfg '，1)、(' is '，5)、(' best '，7)]、K = 1
> **输出** : 4.333333333333
> 
> **输入** : test_list = [('Gfg '，7)、(' best '，7)]，K = 1
> **输出** : 7

**方法#1:使用均值()+生成器表达式**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 mean()执行均值计算任务，并且使用生成器表达式进行迭代。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Kth Index Tuple List Mean
# Using mean() + generator expression
from statistics import mean

# initializing list
test_list = [('Gfg', 4), ('is', 18), ('best', 2), ('for', 5), ('geeks', 1)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 1

# Kth Index Tuple List Mean
# Using mean() + generator expression
res = mean(val[K] for val in test_list)

# printing result
print("The computed mean : " + str(res))
```

**Output : **

```py
The original list is : [('Gfg', 4), ('is', 18), ('best', 2), ('for', 5), ('geeks', 1)]
The computed mean : 6
```

**方法 2:使用 sum() + len() +生成器表达式**
上述函数的组合也可以用来解决这个任务。在这种情况下，我们使用 sum()执行求和计算任务，结果除以使用 len()计算的列表长度。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Kth Index Tuple List Mean
# Using sum() + len() + generator expression
from statistics import mean

# initializing list
test_list = [('Gfg', 4), ('is', 18), ('best', 2), ('for', 5), ('geeks', 1)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 1

# Kth Index Tuple List Mean
# Using sum() + len() + generator expression
res = sum(val[K] for val in test_list) / len(test_list)

# printing result
print("The computed mean : " + str(res))
```

**Output : **

```py
The original list is : [('Gfg', 4), ('is', 18), ('best', 2), ('for', 5), ('geeks', 1)]
The computed mean : 6.0
```