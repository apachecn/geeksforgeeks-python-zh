# Python |通过元组键聚合值

> 原文:[https://www . geeksforgeeks . org/python-按元组键聚合值/](https://www.geeksforgeeks.org/python-aggregate-values-by-tuple-keys/)

有时，在处理记录时，我们可能会遇到这样的问题:我们需要对相似键进行分组，并聚合相似键的值。这可以应用于任何类型的评分。让我们讨论执行这项任务的某些方法。

**方法#1:使用`Counter()` +生成器表达式**
上述功能的组合可用于执行该特定任务。在这种情况下，我们需要首先组合相似的关键元素，聚合任务由`Counter()`执行。

```py
# Python3 code to demonstrate working of
# Aggregate values by tuple keys
# using Counter() + generator expression
from collections import Counter

# initialize list
test_list = [('gfg', 50), ('is', 30), ('best', 100), 
                          ('gfg', 20), ('best', 50)]

# printing original list
print("The original list is : " + str(test_list))

# Aggregate values by tuple keys
# using Counter() + generator expression
res = list(Counter(key for key, num in test_list 
                  for idx in range(num)).items())

# printing result
print("List after grouping : " + str(res))
```

**Output :**

```py
The original list is : [('gfg', 50), ('is', 30), ('best', 100), ('gfg', 20), ('best', 50)]
List after grouping : [('best', 150), ('gfg', 70), ('is', 30)]

```