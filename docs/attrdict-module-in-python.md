# Python 中的属性模块

> 原文:[https://www.geeksforgeeks.org/attrdict-module-in-python/](https://www.geeksforgeeks.org/attrdict-module-in-python/)

AttrDict 是一个麻省理工学院许可的库，它提供映射对象，允许它们的元素作为键和属性被访问。
所以我们可以想到我们导入使用的字典。

**安装:**

要安装 AttrDict，请使用 pip 命令，如下所示:

```py
pip install attrdict
```

安装好之后，让我们通过程序的工作来理解它:

**示例 1 :** 这里我们将展示如何使用模块创建字典对。

## 蟒蛇 3

```py
# importing the module
from attrdict import AttrDict

# creating a dictionary pair
dictionary = AttrDict({"Geeks" : "forGeeks"})

# accessing the value using key
# method 1
print(dictionary.Geeks)

# method 2
print(dictionary["Geeks"])
```

**输出:**

```py
forGeeks
forGeeks
```

**示例 2 :** 制作多个元素的嵌套字典并打印。

## 蟒蛇 3

```py
# importing the module
from attrdict import AttrDict

# creating a dictionary
dictionary = AttrDict({'foo': 'bar',
                       'alpha': {'beta': 'a',
                                 'a': 'a'}})

# printing the values
for key in dictionary:
    print(dictionary[key])
```

**输出:**

```py
bar
{'beta': 'a', 'a': 'a'}
```

**示例 3 :** 向字典中添加另一个字典。

## 蟒蛇 3

```py
# importing the module
from attrdict import AttrDict

# creating the first dictionary
a = {'foo': 'bar', 'alpha': {'beta': 'a', 'a': 'a'}}

# creating the second dictionary
b = {'lorem': 'ipsum', 'alpha': {'bravo': 'b', 'a': 'b'}}

# combining the dictionaries
c = AttrDict(a) + b

print(type(c))
print(c)
```

**输出:**

```py
<class 'attrdict.dictionary.AttrDict'>
AttrDict({'foo': 'bar', 'lorem': 'ipsum', 'alpha': {'beta': 'a', 'bravo': 'b', 'a': 'b'}})
```