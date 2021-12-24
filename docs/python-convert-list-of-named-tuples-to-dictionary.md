# Python–将命名元组列表转换为字典

> 原文:[https://www . geesforgeks . org/python-convert-list-of-named-tuples-to-dictionary/](https://www.geeksforgeeks.org/python-convert-list-of-named-tuples-to-dictionary/)

在本文中，我们将使用 python 将命名元组列表转换为字典。

通过使用 dict()方法，我们可以将一个名为[的元组列表](https://www.geeksforgeeks.org/namedtuple-in-python/)转换为字典。在此之前，我们必须使用 _asdict()方法将其转换为字典。

首先，我们必须使用 _asdict()方法将 namedtuple 转换为每个元素中的字典，然后我们最终使用 dict()方法转换为字典

**语法:**

```
for i in list:
     print(dict(i._asdict()))
```

哪里，

该列表是一个命名元组

**示例** : Python 程序将 namedtuple 转换为字典

## 蟒蛇 3

```
# import named tuple
from collections import namedtuple

# create a named tuple named DETAILS with three columns
DETAILS = namedtuple("DETAILS", "Name, Age, Subject")

# create 5 students
a = [DETAILS("ojaswi", 21, "python"),
     DETAILS("sireesha", 21, "python"),
     DETAILS("gnanesh", 23, "php"),
     DETAILS("priyank", 21, "java"),
     DETAILS("ojaswi", 22, "big-data")]

# convert into dictionary
# using dict method
for i in a:
    print(dict(i._asdict()))
```

**输出:**

> { '姓名':' ojaswi '，'年龄':21 岁，'主题':' python'}
> 
> { '姓名':' sireesha '，'年龄':21 岁，'主题':' python'}
> 
> {“姓名”:“gnanesh”，“年龄”:23，“主题”:“PHP”}
> 
> {“姓名”:“普里扬克”，“年龄”:21 岁，“主题”:“Java”}
> 
> { '姓名':' ojaswi '，'年龄':22 岁，'主题':'大数据' }

**示例:**将 namedtuple 转换为字典的 Python 程序

## 蟒蛇 3

```
# import named tuple
from collections import namedtuple

# create a nmaed tuple named DETAILS with one column
DETAILS = namedtuple("DETAILS", "Name")

# create 5 students
a = [DETAILS("ojaswi"),
     DETAILS("sireesha"),
     DETAILS("gnanesh"),
     DETAILS("priyank"),
     DETAILS("ojaswi")]

# convert into dictionary
# using dict method
for i in a:
    print(dict(i._asdict()))
```

**输出:**

> {'Name': 'ojaswi'}
> 
> {'Name': 'sireesha'}
> 
> " gnanesh "
> 
> {'Name': 'priyank'}
> 
> {'Name': 'ojaswi'}