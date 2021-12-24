# Python–将嵌套元组转换为自定义键字典

> 原文:[https://www . geesforgeks . org/python-convert-nested-tuple-to-custom-key-dictionary/](https://www.geeksforgeeks.org/python-convert-nested-tuple-to-custom-key-dictionary/)

有时，在处理 Python 记录时，我们可能会遇到没有正确列名/标识符的数据，这些数据只能通过它们的索引来识别，但我们打算为它们分配关键字，并以字典的形式呈现。这种问题在 web 开发等领域都有应用。让我们讨论执行这项任务的某些方法。

> **输入** : test_tuple = ((1，' Gfg '，2)，(3，' best '，4))，key =[' key '，' value '，' id']
> **输出** : [{'key': 1，' value': 'Gfg '，' id': 2}，{'key': 3，' value': 'best '，' id': 4}]
> 
> **输入** : test_tuple = test_tuple = ((1，' Gfg '，(2，3))，key =[' key '，' value']
> **输出** : [{'key': 1，' value': 'Gfg'}，{'key': 2，' value': 3}]

**方法一:使用列表理解+词典理解**
以上功能的组合可以用来解决这个问题。在本文中，我们使用字典理解和所有关键字的迭代来分配关键字，并使用列表理解来构建数据。

```
# Python3 code to demonstrate working of 
# Convert Nested Tuple to Custom Key Dictionary
# Using list comprehension + dictionary comprehension

# initializing tuple
test_tuple = ((4, 'Gfg', 10), (3, 'is', 8), (6, 'Best', 10))

# printing original tuple
print("The original tuple : " + str(test_tuple))

# Convert Nested Tuple to Custom Key Dictionary
# Using list comprehension + dictionary comprehension
res = [{'key': sub[0], 'value': sub[1], 'id': sub[2]} 
                               for sub in test_tuple]

# printing result 
print("The converted dictionary : " + str(res))
```

**Output :**

> 原始元组:((4，' Gfg '，10)，(3，' is '，8)，(6，' Best '，10))
> 转换后的字典:[{'key': 4，' value': 'Gfg '，' id': 10}，{'key': 3，' value': 'is '，' id': 8}，{'key': 6，' value': 'Best '，' id': 10}]

**方法二:使用`zip()` +列表理解**
以上功能的组合可以解决这个问题。在本文中，我们使用列表内容分配索引键，并使用 zip()进行映射。在这种情况下，提供了预定义/缩放键的灵活性。

```
# Python3 code to demonstrate working of 
# Convert Nested Tuple to Custom Key Dictionary
# Using zip() + list comprehension

# initializing tuple
test_tuple = ((4, 'Gfg', 10), (3, 'is', 8), (6, 'Best', 10))

# printing original tuple
print("The original tuple : " + str(test_tuple))

# initializing Keys 
keys = ['key', 'value', 'id']

# Convert Nested Tuple to Custom Key Dictionary
# Using zip() + list comprehension
res = [{key: val for key, val in zip(keys, sub)}
                          for sub in test_tuple]

# printing result 
print("The converted dictionary : " + str(res))
```

**Output :**

> 原始元组:((4，' Gfg '，10)，(3，' is '，8)，(6，' Best '，10))
> 转换后的字典:[{'key': 4，' value': 'Gfg '，' id': 10}，{'key': 3，' value': 'is '，' id': 8}，{'key': 6，' value': 'Best '，' id': 10}]