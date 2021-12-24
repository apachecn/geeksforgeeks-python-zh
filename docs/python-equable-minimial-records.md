# Python–等分最小记录

> 原文:[https://www . geesforgeks . org/python-equable-minimal-records/](https://www.geeksforgeeks.org/python-equable-minimial-records/)

有时，在使用 Python 记录时，我们会遇到一个问题，即我们需要提取一个等于某个索引的记录，该索引是其他索引的最小索引。这种问题发生在 web 开发等领域。让我们讨论执行这项任务的某些方法。

> **输入** :
> test_list = [('Gfg '，13，5)、(' is '，13，6)、(' best '，13，2)、(' CS '，13，2)]
> eq_idx = 2，min_idx = 3
> **输出**:【(' best '，13，2)】
> 
> **输入** :
> test_list = [('Gfg '，12，5)、(' is '，12，6)、(' best '，13，2)、(' CS '，13，3)]
> eq_idx = 2，min_idx = 3
> **输出**:【(' Gfg '，12，5)、(' best '，13，2)】

**方法#1:使用列表理解+ `min() + lambda`**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用 min()来提取最小索引值，并使用列表理解和 lambda 函数来执行元素分组任务。

```
# Python3 code to demonstrate working of 
# Equable Minimial Records
# Using min() + list comprehension + lambda

# initializing list
test_list = [('Gfg', 12, 5), ('is', 13, 6), ('best', 12, 2), ('CS', 13, 2)]

# printing original list
print("The original list is : " + str(test_list))

# initializing Equate index 
eq_idx = 2

# initializing min index 
min_idx = 3

# Equable Minimial Records
# Using min() + list comprehension + lambda
res = [min((ele for ele in test_list if ele[eq_idx - 1] == sub),
      key = lambda a: int(a[min_idx - 1]))
      for sub in {b[eq_idx - 1] for b in test_list}]

# printing result 
print("Equable Minimal Records : " + str(res)) 
```

**Output :**

```
The original list is : [('Gfg', 12, 5), ('is', 13, 6), ('best', 12, 2), ('CS', 13, 2)]
Equable Minimal Records : [('best', 12, 2), ('CS', 13, 2)]

```

**方法 2:使用`groupby() + filter()`+λ**
以上功能的组合可以解决这个问题。在本例中，我们使用 groupby()执行分组任务，filter() + lambda 用于匹配条件的任务。

```
# Python3 code to demonstrate working of 
# Equable Minimial Records
# Using groupby() + filter() + lambda
from itertools import groupby

# initializing list
test_list = [('Gfg', 12, 5), ('is', 13, 6), ('best', 12, 2), ('CS', 13, 2)]

# printing original list
print("The original list is : " + str(test_list))

# initializing Equate index 
eq_idx = 2

# initializing min index 
min_idx = 3

# Equable Minimial Records
# Using groupby() + filter() + lambda
res = []
for k, val in groupby(test_list, lambda sub: sub[eq_idx - 1]):
    res.append(min(filter(lambda sub : sub[eq_idx - 1] == k, test_list),
                                   key = lambda sub : sub[min_idx - 1]))
res = list(set(res))

# printing result 
print("Equable Minimal Records : " + str(res)) 
```

**Output :**

```
The original list is : [('Gfg', 12, 5), ('is', 13, 6), ('best', 12, 2), ('CS', 13, 2)]
Equable Minimal Records : [('best', 12, 2), ('CS', 13, 2)]

```