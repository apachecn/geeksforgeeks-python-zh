# Python |提取两个列表中的组合映射

> 原文:[https://www . geesforgeks . org/python-extract-组合拳-二合一映射-列表/](https://www.geeksforgeeks.org/python-extract-combination-mapping-in-two-lists/)

有时，在使用 Python 列表时，我们可能会遇到一个问题，即我们有两个列表，并且需要在所有组合中找到所有可能的映射。这在数学问题中可能有应用。让我们讨论一下解决这个问题的某些方法。

**方法:使用`zip() + product()`**
这些功能可以解决这个问题，并且需要两步来执行。在第一步中，我们使用`product()`找到所有元素的组合，作为第二步的一部分，我们使用`zip()`对第一步的结果进行可能的配对，并输出期望的结果。

```py
# Python3 code to demonstrate working of
# Extract Combination Mapping in two lists
# using zip() + product()
from itertools import product

# initialize lists
test_list1 = [3, 4, 5]
test_list2 = ['x', 'y']

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# Extract Combination Mapping in two lists
# using zip() + product()
res = list(list(zip(test_list1, ele)) for ele in product(test_list2, repeat = len(test_list1)))

# printing result
print("Mapped Combination result : " + str(res))
```

**Output :**

> 原始列表 1 为:[3，4，5]
> 原始列表 2 为:['x '，' y']
> 映射组合结果:[[(3，' x ')，(4，' x ')，(5，' x')]，[(3，' x ')，(5，' y')]，[(3，' x ')，(4，' y '，(5，' x')]，[(3，' x ')，(4，' y '，(5，' y ')，[(3，' y ')，(4，' y '，(5，' y ')，[(3，' y '，(4 '，'