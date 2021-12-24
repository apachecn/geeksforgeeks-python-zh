# Python |迭代时从字典中删除项目

> 原文:[https://www . geesforgeks . org/python-迭代时从字典中删除项目/](https://www.geeksforgeeks.org/python-delete-items-from-dictionary-while-iterating/)

Python 中的 Dictionary 是一个无序的数据值集合，用于像映射一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存键:值对。字典的键必须是唯一的并且是不可变的数据类型，例如字符串、整数和元组，但是键值可以重复并且是任何类型。
让我们看看如何在迭代字典时从字典中删除条目。
**方法#1:使用德尔()方法**

## 蟒蛇 3

```
# Creating a dictionary
myDict = {1: 'Geeks', 2: 'For', 3: 'Geeks'}

# Iterating through the keys
for key in myDict.keys():
    if key == 2:
        del myDict[key]

# Modified Dictionary       
print(myDict)
```

**输出:**

```
{1: 'Geeks', 3: 'Geeks'}
```

上面的代码对 Python2 很有效，但是当我们用 Python3 运行它时，它会抛出以下错误:

```
for key in myDict.keys():
RuntimeError: dictionary changed size during iteration
```

这个运行时错误表示不允许在迭代过程中改变字典的大小(但这是可能的)。现在，让我们看看迭代时从字典中删除条目的所有不同方法。

**方法二:利用字典理解**

## 蟒蛇 3

```
# Creating a dictionary
myDict = {1: 'Geeks', 2: 'For', 3: 'Geeks'}

# Using dictionary comprehension to find list
# keys having value in 3.
delete = [key for key in myDict if key == 3]

# delete the key
for key in delete: del myDict[key]

# Modified Dictionary 
print(myDict)
```

**输出:**

```
{1: 'Geeks', 2: 'For'}
```

**另一种方式:**

## 蟒蛇 3

```
# Creating a dictionary
myDict = {1: 'Geeks', 2: 'For', 3: 'Geeks'}

# Using dictionary comprehension
for key in [key for key in myDict if key == 3]: del myDict[key]

# Modified Dictionary 
print(myDict)
```

**输出:**

```
{1: 'Geeks', 2: 'For'}
```

**方法 3:使用列表(myDict)**

## 蟒蛇 3

```
# Creating a dictionary
myDict = {1: 'Geeks', 2: 'For', 3: 'Geeks'}

# Iterating through the list of keys
for key in list(myDict):
    if key == 2:
        del myDict[key]

# Modified Dictionary    
print(myDict)
```

**输出:**

```
{1: 'Geeks', 3: 'Geeks'}
```

**方法#4:使用键列表**
创建列表删除并添加我们想要删除的所有值的键。遍历列表中的每个键，并不断删除它们。

## 蟒蛇 3

```
# Creating a dictionary
myDict = {1: 'Geeks', 2: 'For', 3: 'Geeks'}

# list of delete keys
delete = []
for key, val in myDict.items():
    if val == 'Geeks':
        delete.append(key)

for i in delete:
    del myDict[i]

# Modified Dictionary    
print(myDict)
```

**输出:**

```
{2: 'For'}
```

当 val == 'Geeks '时，上面的代码将删除所有键:值对。由于“极客”在上面的字典中出现了两次，因此删除了两个值。