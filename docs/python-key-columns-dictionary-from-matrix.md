# Python–来自矩阵的键列字典

> 原文:[https://www . geesforgeks . org/python-key-columns-dictionary-from-matrix/](https://www.geeksforgeeks.org/python-key-columns-dictionary-from-matrix/)

给定矩阵和键列表，用自定义列表键映射每个列值。

> **输入** : test_list1 = [[4，6]，[8，6]]，test _ list 2 =[“Gfg”，“Best”]
> **输出**:{“Gfg”:[4，8]，“Best”:[6，6]}
> **解释**:列式，键值赋值。
> **输入** : test_list1 = [[4]，[6]]，test _ list 2 =[“Gfg”]
> **输出** : {'Gfg': [4，6]}
> **解释**:列方式，键值赋值，只是单个元素列表。

**方法一:使用列表理解+词典理解**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用列表理解来执行提取列值的任务，然后使用字典理解来形成具有列表键的字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Key Columns Dictionary from Matrix
# Using list comprehension + dictionary comprehension

# initializing lists
test_list1 = [[4, 6, 8], [8, 4, 2], [8, 6, 3]]
test_list2 = ["Gfg", "is", "Best"]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# using enumerate to get column numbers
# dictionary comprehension to compile result
res = {key: [sub[idx] for sub in test_list1] for idx, key in enumerate(test_list2)}

# printing result
print("The paired dictionary : " + str(res))
```

**Output**

```
The original list 1 : [[4, 6, 8], [8, 4, 2], [8, 6, 3]]
The original list 2 : ['Gfg', 'is', 'Best']
The paired dictionary : {'Gfg': [4, 8, 8], 'is': [6, 4, 6], 'Best': [8, 2, 3]}
```

**方法 2:使用 zip() + dict()**

这是执行这项任务的另一种方式。在本文中，我们使用 zip()连接键值对，dict()用于转换字典中的结果。不同之处在于，它生成元组而不是列表作为映射值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Key Columns Dictionary from Matrix
# Using zip() + dict()

# initializing lists
test_list1 = [[4, 6, 8], [8, 4, 2], [8, 6, 3]]
test_list2 = ["Gfg", "is", "Best"]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# zip() used to map keys with values and return tuples
# as result
# * operator used to perform unpacking
res = dict(zip(test_list2, zip(*test_list1)))

# printing result
print("The paired dictionary : " + str(res))
```

**Output**

```
The original list 1 : [[4, 6, 8], [8, 4, 2], [8, 6, 3]]
The original list 2 : ['Gfg', 'is', 'Best']
The paired dictionary : {'Gfg': (4, 8, 8), 'is': (6, 4, 6), 'Best': (8, 2, 3)}
```