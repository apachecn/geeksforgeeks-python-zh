# Python–从混合矩阵中提取字符串元素

> 原文:[https://www . geesforgeks . org/python-extract-string-elements-from-mixed-matrix/](https://www.geeksforgeeks.org/python-extract-string-elements-from-mixed-matrix/)

给定一个矩阵，提取所有字符串数据类型的元素。

> **输入** : test_list = [[5，6，3]，[“Gfg”，3]，[9，“best”，4]]
> **输出**:[‘Gfg’，‘best’]
> **解释**:提取所有字符串。
> 
> **输入**:test _ list =[[“Gfg”，3]，[9，“best”，4]]
> **输出**:[“Gfg”，“best”]
> **解释**:提取所有字符串。

**方法一:使用列表理解+ isinstance()**

上述功能的组合可以用来解决这个问题。在本文中，我们使用列表理解迭代嵌套列表，并使用 *isinstance()* 检查字符串实例。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract String elements from Mixed Matrix
# Using list comprehension + isinstance()

# initializing lists
test_list = [[5, 6, 3], ["Gfg", 3, "is"], [9, "best", 4]]

# printing original list
print("The original list : " + str(test_list))

# strings are extracted using isinstance()
res = [ele for sub in test_list for ele in sub if isinstance(ele, str)]

# printing result
print("The String instances : " + str(res))
```

**Output**

```
The original list : [[5, 6, 3], ['Gfg', 3, 'is'], [9, 'best', 4]]
The String instances : ['Gfg', 'is', 'best']

```

**方法 2:使用 chain.from_iterables() +列表理解+ isinstance()**

这是执行这项任务的另一种方式。将整个矩阵展平，然后将*应用于其上，以检查展平列表中的字符串元素。*

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Extract String elements from Mixed Matrix
# Using chain.from_iterables + list comprehension + isinstance()
from itertools import chain

# initializing lists
test_list = [[5, 6, 3], ["Gfg", 3, "is"], [9, "best", 4]]

# printing original list
print("The original list : " + str(test_list))

# strings are extracted using isinstance()
# using chain.from_iterables()
res = [ele for ele in chain.from_iterable(test_list) if isinstance(ele, str)]

# printing result
print("The String instances : " + str(res))
```

**Output**

```
The original list : [[5, 6, 3], ['Gfg', 3, 'is'], [9, 'best', 4]]
The String instances : ['Gfg', 'is', 'best']

```