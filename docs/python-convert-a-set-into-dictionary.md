# Python |将一个集合转换成字典

> 原文:[https://www . geesforgeks . org/python-convert-a-set-in-dictionary/](https://www.geeksforgeeks.org/python-convert-a-set-into-dictionary/)

在日常编码和 web 开发中，有时我们需要将一种数据结构转换成另一种数据结构来处理各种操作和问题。比如我们可能想从给定的集合元素中得到一个字典。
我们来讨论几个给定集合转换成字典的方法。

**方法#1:** 使用 fromkeys()

## 蟒蛇 3

```
# Python code to demonstrate
# converting set into dictionary
# using fromkeys()

# initializing set
ini_set = {1, 2, 3, 4, 5}

# printing initialized set
print ("initial string", ini_set)
print (type(ini_set))

# Converting set to dictionary
res = dict.fromkeys(ini_set, 0)

# printing final result and its type
print ("final list", res)
print (type(res))
```

**Output:** 

```
initial string {1, 2, 3, 4, 5}
<class 'set'>
final list {1: 0, 2: 0, 3: 0, 4: 0, 5: 0}
<class 'dict'>
```

**方法 2:** 使用字典理解

## 蟒蛇 3

```
# Python code to demonstrate
# converting set into dictionary
# using dict comprehension

# initializing set
ini_set = {1, 2, 3, 4, 5}

# printing initialized set
print ("initial string", ini_set)
print (type(ini_set))

str = 'fg'
# Converting set to dict
res = {element:'Geek'+str for element in ini_set}

# printing final result and its type
print ("final list", res)
print (type(res))
```

**Output:** 

```
initial string {1, 2, 3, 4, 5}
<class 'set'>
final list {1: 'Geek', 2: 'Geek', 3: 'Geek', 4: 'Geek', 5: 'Geek'}
<class 'dict'>
```