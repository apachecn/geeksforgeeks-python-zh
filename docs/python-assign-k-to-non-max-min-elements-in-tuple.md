# Python–将 K 分配给元组中的非最大最小元素

> 原文:[https://www . geesforgeks . org/python-assign-k-to-non-max-min-elements in tuple/](https://www.geeksforgeeks.org/python-assign-k-to-non-max-min-elements-in-tuple/)

有时，在处理 Python 数据时，我们会遇到一个问题，即我们需要根据特定的条件分配特定的值。条件之一可以是非最大、最小元素。这种任务可能出现在日常编程和竞争性编程的许多应用中。让我们讨论执行这项任务的某些方法。

> **输入** :
> 测试 _ 元组= (3，6，3，6，34，34)
> K =无
> T5】输出 : (3，无，3，无，34，34)
> 
> **输入** :
> 测试 _ 元组= (3，34)
> K =无
> T5】输出 : (3，34)

**方法一:使用`max() + min() + tuple()` +循环**
以上功能的组合可以解决这个问题。在本文中，我们使用 min()和 max()以及蛮力来执行寻找最小和最大元素的任务，以将所有例外元素分配给 k。

```
# Python3 code to demonstrate working of 
# Assign K to Non Max-Min elements in Tuple
# Using min() + max() + loop + tuple()

# initializing tuple
test_tuple = (5, 6, 3, 6, 10, 34)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# initializing K 
K = 4

# Assign K to Non Max-Min elements in Tuple
# Using min() + max() + loop + tuple()
res = []
for ele in test_tuple:
    if ele not in [max(test_tuple), min(test_tuple)]:
        res.append(K)
    else:
        res.append(ele)
res = tuple(res)

# printing result 
print("The tuple after conversion: " + str(res))
```

**Output :**

```
The original tuple : (5, 6, 3, 6, 10, 34)
The tuple after conversion: (4, 4, 3, 4, 4, 34)

```

**方法#2:使用生成器表达式+ `max() + min() + tuple()`**
这是一种可以执行该任务的线性方法。在这种情况下，我们提取所有元素，并使用生成器表达式分配适当的条件。

```
# Python3 code to demonstrate working of 
# Assign K to Non Max-Min elements in Tuple
# Using generator expression + max() + min() + tuple()

# initializing tuple
test_tuple = (5, 6, 3, 6, 10, 34)

# printing original tuple
print("The original tuple : " + str(test_tuple))

# initializing K 
K = 4

# Assign K to Non Max-Min elements in Tuple
# Using generator expression + max() + min() + tuple()
res = tuple(ele if ele in [min(test_tuple), max(test_tuple)] else K for ele in test_tuple)

# printing result 
print("The tuple after conversion: " + str(res))
```

**Output :**

```
The original tuple : (5, 6, 3, 6, 10, 34)
The tuple after conversion: (4, 4, 3, 4, 4, 34)

```