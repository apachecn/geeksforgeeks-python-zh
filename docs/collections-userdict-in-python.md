# 收藏。Python 中的用户字典

> 原文:[https://www . geesforgeks . org/collections-user dict-in-python/](https://www.geeksforgeeks.org/collections-userdict-in-python/)

用于像地图一样存储数据值的无序数据值集合在 Python 中被称为**字典**。与其他只保存单个值作为元素的数据类型不同，字典保存键:值对。字典中提供了键值，以使其更加优化。

**注:**详见 [Python 词典](https://www.geeksforgeeks.org/python-dictionary/)

## 收藏品。用户字典

Python 支持一个[字典](https://www.geeksforgeeks.org/python-dictionary/)，就像**集合**模块中的一个名为**用户字典**的容器。这个类充当字典对象的包装类。当一个人想要创建一个自己的带有一些修改的功能或一些新功能的字典时，这个类是有用的。它可以被认为是向字典中添加新行为的一种方式。这个类将一个字典实例作为参数，并模拟一个保存在常规字典中的字典。该字典可由该类的数据属性访问。

**语法:**

```
collections.UserDict([initialdata])
```

**例 1:**

## 蟒 3

```
# Python program to demonstrate
# userdict

from collections import UserDict

d = {'a':1,
    'b': 2,
    'c': 3}

# Creating an UserDict
userD = UserDict(d)
print(userD.data)

# Creating an empty UserDict
userD = UserDict()
print(userD.data)
```

**输出:**

```
{'a': 1, 'b': 2, 'c': 3}
{}
```

**示例 2:** 让我们创建一个从 UserDict 继承的类来实现一个定制的字典。

## 蟒 3

```
# Python program to demonstrate
# userdict

from collections import UserDict

# Creating a Dictionary where
# deletion is not allowed
class MyDict(UserDict):

    # Function to stop deletion
    # from dictionary
    def __del__(self):
        raise RuntimeError("Deletion not allowed")

    # Function to stop pop from
    # dictionary
    def pop(self, s = None):
        raise RuntimeError("Deletion not allowed")

    # Function to stop popitem
    # from Dictionary
    def popitem(self, s = None):
        raise RuntimeError("Deletion not allowed")

# Driver's code
d = MyDict({'a':1,
    'b': 2,
    'c': 3})

print("Original Dictionary")
print(d)

d.pop(1)
```

**输出:**

```
Original Dictionary
{'a': 1, 'c': 3, 'b': 2}
```

```
Traceback (most recent call last):
  File "/home/3ce2f334f5d25a3e24d10d567c705ce6.py", line 35, in 
    d.pop(1)
  File "/home/3ce2f334f5d25a3e24d10d567c705ce6.py", line 20, in pop
    raise RuntimeError("Deletion not allowed")
RuntimeError: Deletion not allowed
Exception ignored in: 
Traceback (most recent call last):
  File "/home/3ce2f334f5d25a3e24d10d567c705ce6.py", line 15, in __del__
RuntimeError: Deletion not allowed
```