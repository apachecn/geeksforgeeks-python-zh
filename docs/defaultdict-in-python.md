# python 中的 default dict

> 原文:[https://www.geeksforgeeks.org/defaultdict-in-python/](https://www.geeksforgeeks.org/defaultdict-in-python/)

[Python 中的字典](https://www.geeksforgeeks.org/python-dictionary/)是一个无序的数据值集合，用于像地图一样存储数据值。与其他只保存单个值作为元素的数据类型不同，字典保存键值对。在字典中，关键字必须是唯一且不可变的。这意味着 Python 元组可以是关键字，而 Python 列表不能。字典可以通过将一系列元素放在花括号{}中来创建，用“逗号”分隔。
T3】例:

## 蟒蛇 3

```
# Python program to demonstrate
# dictionary

Dict = {1: 'Geeks', 2: 'For', 3: 'Geeks'}
print("Dictionary:")
print(Dict)
print(Dict[1])

# Uncommenting this print(Dict[4])
# will raise a KeyError as the
# 4 is not present in the dictionary
```

**输出:**

```
Dictionary:
{1: 'Geeks', 2: 'For', 3: 'Geeks'}
Geeks
```

```
Traceback (most recent call last):
  File "/home/1ca83108cc81344dc7137900693ced08.py", line 11, in 
    print(Dict[4])
KeyError: 4
```

有时，当出现 KeyError 时，它可能会成为一个问题。为了克服这一点，Python 引入了另一个类似于名为 **Defaultdict** 的容器的字典，它存在于集合模块中。
**注:**详见 [Python 词典](https://www.geeksforgeeks.org/python-dictionary/)。

## DefaultDict(预设字典)

**Defaultdict** 是模块**集合**中的一个类似[词典](https://www.geeksforgeeks.org/python-dictionary/)的容器。Defaultdict 是字典类的一个子类，它返回一个类似字典的对象。字典和 defaltdict 的功能几乎相同，除了 defaltdict 从不引发 KeyError。它为不存在的键提供默认值。

> **语法:**default dict(default _ factory)
> 参数:
> 
> *   **default_factory:** 为定义的字典返回默认值的函数。如果这个参数不存在，那么字典会引发一个键错误。

**示例:**

## 蟒蛇 3

```
# Python program to demonstrate
# defaultdict

from collections import defaultdict

# Function to return a default
# values for keys that is not
# present
def def_value():
    return "Not Present"

# Defining the dict
d = defaultdict(def_value)
d["a"] = 1
d["b"] = 2

print(d["a"])
print(d["b"])
print(d["c"])
```

**输出:**

```
1
2
Not Present 
```

## 违约的内部运作

Defaultdict 除了标准的字典操作之外，还添加了一个可写的实例变量和一个方法。实例变量是 default_factory 参数，提供的方法是 __missing__。

*   **Default_factory:** 是返回定义字典默认值的函数。如果这个参数不存在，那么字典会引发一个键错误。
    T3】例:

## 蟒蛇 3

```
# Python program to demonstrate
# default_factory argument of
# defaultdict

from collections import defaultdict

# Defining the dict and passing
# lambda as default_factory argument
d = defaultdict(lambda: "Not Present")
d["a"] = 1
d["b"] = 2

print(d["a"])
print(d["b"])
print(d["c"])
```

**输出:**

```
1
2
Not Present
```

*   **__missing__():** 此函数用于为字典提供默认值。此函数将 default_factory 作为参数，如果此参数为 None，则会引发一个 KeyError，否则它会为给定的键提供一个默认值。当找不到请求的键时，这个方法基本上由 dict 类的 __getitem__()方法调用。__getitem__()引发或返回 __missing__()返回的值。方法。
    T3】例:

## 蟒蛇 3

```
# Python program to demonstrate
# defaultdict

from collections import defaultdict

# Defining the dict
d = defaultdict(lambda: "Not Present")
d["a"] = 1
d["b"] = 2

# Provides the default value
# for the key
print(d.__missing__('a'))
print(d.__missing__('d'))
```

**输出:**

```
Not Present
Not Present 
```

## 使用列表作为默认工厂

当 list 类作为 default_factory 参数传递时，就会用 list 的值创建一个 defaultdict。
**例:**

## 蟒蛇 3

```
# Python program to demonstrate
# defaultdict

from collections import defaultdict

# Defining a dict
d = defaultdict(list)

for i in range(5):
    d[i].append(i)

print("Dictionary with values as list:")
print(d)
```

**输出:**

```
Dictionary with values as list:
defaultdict(<class 'list'>, {0: [0], 1: [1], 2: [2], 3: [3], 4: [4]})
```

## 使用 int 作为默认工厂

当 int 类作为 default_factory 参数传递时，就会创建一个默认值为零的 defaultdict。
**例:**

## 蟒蛇 3

```
# Python program to demonstrate
# defaultdict

from collections import defaultdict

# Defining the dict
d = defaultdict(int)

L = [1, 2, 3, 4, 2, 4, 1, 2]

# Iterate through the list
# for keeping the count
for i in L:

    # The default value is 0
    # so there is no need to
    # enter the key first
    d[i] += 1

print(d)
```

**输出:**

```
defaultdict(<class 'int'>, {1: 2, 2: 3, 3: 1, 4: 2})
```