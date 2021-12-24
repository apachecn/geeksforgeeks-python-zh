# Python–将矩阵转换为集合的集合

> 原文:[https://www . geesforgeks . org/python-convert-matrix-to-set-of-set/](https://www.geeksforgeeks.org/python-convert-matrix-to-sets-of-set/)

在本文中，任务是编写 Python 程序将矩阵转换为集合的集合。

**示例:**

> **输入:** test_list = [[5，6，3]，[1，7，9]，[8，2，0]]
> 
> **输出:** {frozenset({8，0，2})，frozenset({1，9，7})，frozenset({3，5，6})}
> 
> **解释** **:** 转换为多组冰冻集以保持不可移动和可折叠。
> 
> **输入:** test_list = [[5，6，3]，[1，7，9]]
> 
> **输出:** {frozenset({1，9，7})，frozenset({3，5，6})}
> 
> **解释:**转换为 frozensets 集合，以保持不可移植和可散列。

**方法#1:使用**[**set()**](https://www.geeksforgeeks.org/python-set-method/)**+**[**frozenset()**](https://www.geeksforgeeks.org/frozenset-in-python/)**+发电机表达式**

在这种情况下，我们在生成器表达式中执行迭代直到矩阵得到内部集合，并且使用集合()将外部容器转换为集合。内部容器需要是 hashable，因此必须是 frozenset()才能创建。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Matrix to Sets of Set
# Using set() + frozenset() + generator expression

# initializing list
test_list = [[5, 6, 3], [1, 7, 9], [8, 2, 0]]

# printing original list
print("The original list is : " + str(test_list))

# frozenset() to get inner elements hashable required for set()
res = set(frozenset(sub) for sub in test_list)

# printing result
print("Converted set Matrix : " + str(res))
```

**输出:**

> 原始列表为:[[5，6，3]，[1，7，9]，[8，2，0]]
> 
> 转换集矩阵:{frozenset({8，0，2})，frozenset({1，9，7})，frozenset({3，5，6})

**方法二:使用** [**地图()**](https://www.geeksforgeeks.org/python-map-function/)**+frozenset()+set()**

在本例中，map()用于扩展将内部容器转换为 frozenset()的逻辑。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert Matrix to Sets of Set
# Using map() + frozenset() + set()

# initializing list
test_list = [[5, 6, 3], [1, 7, 9], [8, 2, 0]]

# printing original list
print("The original list is : " + str(test_list))

# map() to extend logic to inner elements
res = set(map(frozenset, test_list))

# printing result
print("Converted set Matrix : " + str(res))
```

**输出:**

> 原始列表为:[[5，6，3]，[1，7，9]，[8，2，0]]
> 
> 转换集矩阵:{frozenset({8，0，2})，frozenset({1，9，7})，frozenset({3，5，6})