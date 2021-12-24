# Python 字典项()方法

> 原文:[https://www . geesforgeks . org/python-dictionary-items-method/](https://www.geeksforgeeks.org/python-dictionary-items-method/)

**Python 中的 Dictionary** 是一个无序的数据值集合，用于像映射一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存 key : value pair。
在 Python 字典中， **items()** 方法用于返回所有字典关键字都有值的列表。

> **语法:**dictionary . items()
> T3】参数:此方法不取参数。
> **返回:**一个视图对象，显示给定字典的(键，值)元组对的列表。

**示例#1:**

## 蟒蛇 3

```
# Python program to show working
# of items() method in Dictionary

# Dictionary with three items 
Dictionary1 = { 'A': 'Geeks', 'B': 4, 'C': 'Geeks' }

print("Dictionary items:")

# Printing all the items of the Dictionary
print(Dictionary1.items())
```

**输出:**

```
Dictionary items:
dict_items([('A', 'Geeks'), ('B', 4), ('C', 'Geeks')])

```

列表中这些项目的顺序可能不总是相同的。

**示例#2:** 显示字典修改后项目()的工作情况。

## 蟒蛇 3

```
# Python program to show working
# of items() method in Dictionary

# Dictionary with three items 
Dictionary1 = { 'A': 'Geeks', 'B': 4, 'C': 'Geeks' }

print("Original Dictionary items:")

items = Dictionary1.items()

# Printing all the items of the Dictionary
print(items)

# Delete an item from dictionary
del[Dictionary1['C']]
print('Updated Dictionary:')
print(items)
```

**输出:**

```
Original Dictionary items:
dict_items([('A', 'Geeks'), ('C', 'Geeks'), ('B', 4)])
Updated Dictionary:
dict_items([('A', 'Geeks'), ('B', 4)])

```

如果词典随时更新，更改会自动反映在视图对象中。