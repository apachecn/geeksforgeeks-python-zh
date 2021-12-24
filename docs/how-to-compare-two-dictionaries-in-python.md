# 如何比较 Python 中的两本词典？

> 原文:[https://www . geesforgeks . org/如何比较两本 python 词典/](https://www.geeksforgeeks.org/how-to-compare-two-dictionaries-in-python/)

在本文中，我们将讨论如何比较 Python 中的两个字典。众所周知，什么是字典，但有时我们可能需要比较两本字典。让我们看看做同样事情的不同方法。

**方法 1:** 使用==运算符。

## 计算机编程语言

```
dict1 = {'Name': 'asif', 'Age': 5}
dict2 = {'Name': 'lalita', 'Age': 78}

if dict1 == dict2:
    print "dict1 is equal to dict2"
else:
    print "dict1 is not equal to dict2"
```

**输出:**

```
dict1 is not equal to dict2
```

**方法 2:** 使用 DeepDiff 模块

该模块用于查找字典、iterables、strings 和其他对象之间的深层差异。要安装此模块，请在终端中键入以下命令。

```
pip install deepdiff
```

## 计算机编程语言

```
from deepdiff import DeepDiff

a = {'Name': 'asif', 'Age': 5}
b = {'Name': 'lalita', 'Age': 78}

diff = DeepDiff(a, b)

print(diff)
```

**输出:**

> { ' values _ changed ':{ " root[' Name ']":{ ' new _ value ':' lalita '，' old_value': 'asif'}，" root['Age']": {'new_value': 78，' old_value': 5}}}