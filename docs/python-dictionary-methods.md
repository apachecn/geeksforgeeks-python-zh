# Python 字典方法

> 原文:[https://www.geeksforgeeks.org/python-dictionary-methods/](https://www.geeksforgeeks.org/python-dictionary-methods/)

[**【Python 词典】**](https://www.geeksforgeeks.org/python-dictionary/) 就像一张地图，用来以键:值对的形式存储数据。Python 提供了各种内置函数来处理字典。在本文中，我们将看到 Python 提供的用于字典的所有函数的列表。

## 访问字典

以下函数可用于访问字典项目(键和值)。

*   [**get():**](https://www.geeksforgeeks.org/get-method-dictionaries-python/) 该函数返回给定键的值
*   [**keys():**](https://www.geeksforgeeks.org/python-dictionary-keys-method/) 该函数返回一个视图对象，该对象按照插入顺序显示字典中所有键的列表
*   [**values():**](https://www.geeksforgeeks.org/python-dictionary-values/) 该函数返回给定字典中所有可用值的列表
*   [**items():**](https://www.geeksforgeeks.org/python-dictionary-items-method/) 该函数返回所有字典键都有值的列表

**示例:**访问字典项目。

## 蟒蛇 3

```py
# Python program to demonstrate working
# of dictionary copy
dic = {1:'geeks', 2:'for', 3:'geeks'}
print('original: ', dic)

# Accessing value for key
print(dic.get(1))

# Accessing keys for the dictionary
print(dic.keys())

# Accessing keys for the dictionary
print(dic.values())

# Printing all the items of the Dictionary
print(dic.items())
```

**Output**

```py
original:  {1: 'geeks', 2: 'for', 3: 'geeks'}
geeks
dict_keys([1, 2, 3])
dict_values(['geeks', 'for', 'geeks'])
dict_items([(1, 'geeks'), (2, 'for'), (3, 'geeks')])
```

## Python 字典方法表

<figure class="table">

| 功能名称 | 描述 |
| --- | --- |
| [晴()](https://www.geeksforgeeks.org/python-dictionary-clear/) | 从字典中移除所有项目 |
| [副本()](https://www.geeksforgeeks.org/python-dictionary-copy/) | 返回字典的一个简单副本 |
| [fromkeys()](https://www.geeksforgeeks.org/python-dictionary-fromkeys-method/) | 根据给定的序列创建字典 |
| [get()](https://www.geeksforgeeks.org/get-method-dictionaries-python/) | 返回给定键的值 |
| [项()](https://www.geeksforgeeks.org/python-dictionary-items-method/) | 返回包含所有字典键和值的列表 |
| [键()](https://www.geeksforgeeks.org/python-dictionary-keys-method/) | 返回一个 view 对象，该对象按插入顺序显示字典中所有键的列表 |
| [pop()](https://www.geeksforgeeks.org/python-dictionary-pop-method/) | 返回并移除具有给定键的元素 |
| [灰分()](https://www.geeksforgeeks.org/python-dictionary-popitem-method/) | 从字典中返回并移除键值对 |
| [集合默认值（）](https://www.geeksforgeeks.org/python-dictionary-setdefault-method/) | 如果关键字在字典中，则返回该关键字的值，否则将带有值的关键字插入字典 |
| [更新()](https://www.geeksforgeeks.org/python-dictionary-update-method/) | 用另一个字典中的元素更新字典 |
| [值()](https://www.geeksforgeeks.org/python-dictionary-values/) | 返回给定字典中所有可用值的列表 |

</figure>

**注:**关于 Python 词典的更多信息，请参考 [Python 词典教程](https://www.geeksforgeeks.org/python-dictionary/)。