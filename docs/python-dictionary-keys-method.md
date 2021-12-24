# Python 字典键()方法

> 原文:[https://www . geesforgeks . org/python-dictionary-keys-method/](https://www.geeksforgeeks.org/python-dictionary-keys-method/)

**Python 中的 Dictionary** 是数据值的集合，它只保持插入的顺序，用于像映射一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存 key: value pair。

**keys()** 方法在 Python Dictionary 中，返回一个 view 对象，该对象按照插入顺序显示字典中所有键的列表。

> **语法:**dict . keys()
> T3】参数:没有参数。
> **返回:**返回显示所有按键的视图对象。该视图对象根据字典中的变化而变化。

**示例#1:**

## 蟒蛇 3

```
# Python program to show working
# of keys in Dictionary

# Dictionary with three keys
Dictionary1 = {'A': 'Geeks', 'B': 'For', 'C': 'Geeks'}

# Printing keys of dictionary
print(Dictionary1.keys())

# Creating empty Dictionary
empty_Dict1 = {}

# Printing keys of Empty Dictionary
print(empty_Dict1.keys())
```

**输出:**

```
dict_keys(['A', 'B', 'C'])
dict_keys([])
```

**注意:**列表中这些键值的顺序可能不总是相同的。

**示例 2:** 展示词典更新的工作原理

## 蟒蛇 3

```
# Python program to show updation
# of keys in Dictionary

# Dictionary with two keys
Dictionary1 = {'A': 'Geeks', 'B': 'For'}

# Printing keys of dictionary
print("Keys before Dictionary Updation:")
keys = Dictionary1.keys()
print(keys)

# adding an element to the dictionary
Dictionary1.update({'C':'Geeks'})

print('\nAfter dictionary is updated:')
print(keys)
```

**输出:**

```
Keys before Dictionary Updation:
dict_keys(['B', 'A'])

After dictionary is updated:
dict_keys(['B', 'A', 'C'])
```

在这里，当字典更新时，键也会自动更新以显示更改。

**实际应用:**key()可以用来访问字典的元素，就像我们对列表可以做的那样，没有 key()的使用，没有其他机制提供通过索引作为列表访问字典 key 的手段。下面的例子说明了这一点。

**例 3:** 演示按键的实际应用()

## 蟒蛇 3

```
# Python program to demonstrate
# working of keys()

# initializing dictionary
test_dict = { "geeks" : 7, "for" : 1, "geeks" : 2 }

# accessing 2nd element using naive method
# using loop
j = 0
for i in test_dict:
    if (j == 1):
        print ('2nd key using loop : ' + i)
    j = j + 1

# accessing 2nd element using keys()
print ('2nd key using keys() : ' + test_dict.keys()[1])
```

**输出:**

```
2nd key using loop : for
TypeError: 'dict_keys' object does not support indexing 
```

**注意:**第二种方法不起作用，因为 Python 3 中的 ***dict_keys*** 不支持索引。