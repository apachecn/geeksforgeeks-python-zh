# Python |给元组添加字典

> 原文:[https://www . geesforgeks . org/python-add-dictionary-to-tuple/](https://www.geeksforgeeks.org/python-add-dictionary-to-tuple/)

有时，在处理数据时，我们会遇到一个问题，即需要向元组中添加一个 Python 字典形式的新记录。在复合属性的情况下，这种应用程序可以进入 web 开发领域。让我们讨论执行这项任务的某些方法。
**方法#1:使用 list() + append + tuple()**
这个方法可以用来解决这个问题。在这种情况下，我们只需将元组转换为列表，然后执行列表追加，然后使用 tuple()将列表重新转换为元组。

**示例:**

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Add dictionary to tuple
# using append() + tuple() + list comprehension

# initialize tuple
test_tup = (4, 5, 6)

# printing original tuple
print("The original tuple : " + str(test_tup))

# initialize dictionary
test_dict = {"gfg" : 1, "is" : 2, "best" : 3}

# Add dictionary to tuple
# using append() + tuple() + list comprehension
test_tup = list(test_tup)
test_tup.append(test_dict)
test_tup = tuple(test_tup)

# printing result
print("Tuple after addition of dictionary : " + str(test_tup))
```

**Output : **

```py
The original tuple : (4, 5, 6)
Tuple after addition of dictionary : (4, 5, 6, {'best': 3, 'is': 2, 'gfg': 1})
```