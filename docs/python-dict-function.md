# Python dict()函数

> 原文:[https://www.geeksforgeeks.org/python-dict-function/](https://www.geeksforgeeks.org/python-dict-function/)

**Python dict()函数**用于创建 [Python 字典](https://www.geeksforgeeks.org/python-dictionary/)。字典是键值对的集合。字典是可变的数据结构，即字典中的数据可以修改。在 python 3.6 和更低版本中，dictionary 是键值对的无序集合，但在 python 3.7 中，dictionary 是有序的数据结构。字典是一种索引数据结构，即字典的内容可以通过使用索引来访问，在字典中，关键字用作索引。

### **示例 1:** 使用关键字参数创建字典

我们可以将关键字参数作为参数传递，所需的值将成为字典的键和值。

**语法:**

```
class dict(**kwarg)
```

## 蟒蛇 3

```
# passing keyword arguments to dict() method
myDict = dict(a=1, b=2, c=3, d=4)

print(myDict)
```

**输出:**

```
{'a': 1, 'b': 2, 'c': 3, 'd': 4}
```

### **示例 2** :通过映射键和值来创建字典

也可以使用冒号将键映射到值，多个键-值对可以用逗号分隔，并传递给 dict()。

**语法:**

```
class dict(mapping, **kwarg)
```

## 蟒蛇 3

```
# passing key-values pairs mapped by colon to dict function
myDict = dict({'a': 1, 'b': 2, 'c': 3})

print(myDict)
```

**输出:**

```
{'a': 1, 'b': 2, 'c': 3}
```

### **示例 3:** 使用可条目创建字典

键和值可以像列表或元组一样以可条目的形式传递给 dict()，以形成字典，关键字参数也可以传递给 dict()。

**语法:**

```
class dict(iterable, **kwarg)
```

## 蟒蛇 3

```
# A list of key value pairs is passesd and
# keyword argument is also passed
myDict = dict([('a', 1), ('b', 2), ('c', 3)], d=4)

print(myDict)
```

**输出:**

```
{'a': 1, 'b': 2, 'c': 3, 'd': 4}
```