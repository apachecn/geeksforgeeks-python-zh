# Python–在字典中追加字典键和值(按顺序)

> 原文:[https://www . geesforgeks . org/python-append-dictionary-key-and-values-in-order-in-dictionary/](https://www.geeksforgeeks.org/python-append-dictionary-keys-and-values-in-order-in-dictionary/)

给定一个字典，在列表中执行关键字后接值的追加。

> **输入**:test _ dict = {“Gfg”:1、“is”:2、“Best”:3 }
> **输出**:[‘Gfg’、‘is’、‘Best’，1、2、3]
> **解释**:列表中所有值之前的所有键。
> 
> **输入**:test _ dict = {“Gfg”:1、【最佳】:3}
> **输出**:【‘Gfg’、‘最佳’、1、3】
> **解释**:列表中所有值前的所有键。

**方法#1:使用 list()+key()+values()**

这是执行这项任务的方法之一。在本例中，我们使用 key()和值()提取键和值，然后使用 list()转换为列表，并按顺序执行追加。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Append Dictionary Keys and Values ( In order ) in dictionary
# Using values() + keys() + list()

# initializing dictionary
test_dict = {"Gfg" : 1, "is" :  3, "Best" : 2}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# + operator is used to perform adding keys and values
res = list(test_dict.keys()) + list(test_dict.values())

# printing result 
print("The ordered keys and values : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': 1, 'is': 3, 'Best': 2}
The ordered keys and values : ['Gfg', 'is', 'Best', 1, 3, 2]

```

**方法 2:使用 chain()+key()+values()**

这是执行这项任务的方法之一。在本文中，我们使用 chain()将键和值按顺序绑定在一起。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Append Dictionary Keys and Values ( In order ) in dictionary
# Using chain() + keys() + values()
from itertools import chain

# initializing dictionary
test_dict = {"Gfg" : 1, "is" :  3, "Best" : 2}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# chain() is used for concatenation
res = list(chain(test_dict.keys(), test_dict.values()))

# printing result 
print("The ordered keys and values : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': 1, 'is': 3, 'Best': 2}
The ordered keys and values : ['Gfg', 'is', 'Best', 1, 3, 2]

```