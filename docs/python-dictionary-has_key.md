# Python | Dictionary has _ key()

> 原文:[https://www.geeksforgeeks.org/python-dictionary-has_key/](https://www.geeksforgeeks.org/python-dictionary-has_key/)

[**Python 中的 Dictionary**](https://www.geeksforgeeks.org/python-set-4-dictionary-keywords-python/) 是一个无序的数据值集合，用于像地图一样存储数据值，与其他只保存单个值作为元素的数据类型不同，Dictionary 保存 **key : value** 对。

在 Python 字典中， **has_key()** 方法返回 true 如果字典中存在指定的键，否则返回 false。

> **语法:**dict . has _ key(key)
> T3】参数:
> 
> *   **键**–这是要在字典中搜索的键。
> 
> **返回:**如果给定的键在字典中可用，方法返回真，否则返回假。

**示例#1:**

## 计算机编程语言

```
# Python program to show working
# of has_key() method in Dictionary

# Dictionary with three items
Dictionary1 = {'A': 'Geeks', 'B': 'For', 'C': 'Geeks'}

# Dictionary to be checked
print("Dictionary to be checked: ")
print(Dictionary1)

# Use of has_key() to check
# for presence of a key in Dictionary
print(Dictionary1.has_key('A'))
print(Dictionary1.has_key('For'))
```

**输出:**

```
Dictionary to be checked: 
{'A': 'Geeks', 'C': 'Geeks', 'B': 'For'}
True
False
```

**例 2:**

## 计算机编程语言

```
# Python program to show working
# of has_key() method in Dictionary

# Dictionary with three items
Dictionary2 = {1: 'Welcome', 2: 'To', 3: 'Geeks'}

# Dictionary to be checked
print("Dictionary to be checked: ")
print(Dictionary2)

# Use of has_key() to check
# for presence of a key in Dictionary
print(Dictionary2.has_key(1))
print(Dictionary2.has_key('To'))
```

**输出:**

```
Dictionary to be checked: 
{1: 'Welcome', 2: 'To', 3: 'Geeks'}
True
False
```

**注意:** dict.has_key()已经从 Python 3.x 中移除

has_key()在 Python 3 中已被删除。运算符 中的 [**用于检查字典中是否存在指定的键。**](https://www.geeksforgeeks.org/python-membership-identity-operators-not-not/)

**示例:**

## 蟒蛇 3

```
# Python Program to search a key in Dictionary
# Using in operator

dictionary = {1: "Geeks", 2: "For", 3: "Geeks"}

print("Dictionary: {}".format(dictionary))

# Return True if Present.
if 1 in dictionary: # or "dictionary.keys()"
    print(dictionary[1])
else:
    print("{} is Absent".format(1))

# Return False if not Present.
if 5 in dictionary.keys():
    print(dictionary[5])
else:
    print("{} is Absent".format(5))
```

**输出:**

```
Dictionary: {1:"Geeks",2:"For",3:"Geeks"}
Geeks
5 is Absent 
```