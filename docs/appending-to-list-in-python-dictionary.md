# 追加到 Python 字典中的列表

> 原文:[https://www . geeksforgeeks . org/追加到 python 字典列表/](https://www.geeksforgeeks.org/appending-to-list-in-python-dictionary/)

在本文中，我们将看到如何在 Python 字典中向列表追加内容。

## 方法 1:对空值的键使用+=符号

在这个方法中，我们将使用+=运算符向字典中添加一个列表，为此，我们将获取一个字典，然后将元素作为列表添加到字典中。

## 蟒蛇 3

```py
Details = {"Destination": "China", 
           "Nstionality": "Italian", "Age": []}
Details["Age"] += [20, "Twenty"]
print(Details)
```

**输出:**

```py
{'Destination': 'China', 'Nstionality': 'Italian', 'Age': [20, 'Twenty']}
```

您也可以追加一个项目。

## 方法二:使用 [if 语句](https://www.geeksforgeeks.org/python-if-else/)

在这个方法中，我们将使用条件来检查关键字，然后将列表追加到字典中。

## 蟒蛇 3

```py
Details = {}
Details["Age"] = [20]
print(Details)

if "Age" in Details:
    Details["Age"].append("Twenty")
    print(Details)
```

**输出:**

```py
{'Age': [20]}
{'Age': [20, 'Twenty']}
```

## 方法三:使用 [defaultdict()](https://www.geeksforgeeks.org/defaultdict-in-python/) 方法

在这个方法中，我们使用的是 defaultdict()函数，它是 collections 模块的一部分。您必须从 collections 模块导入函数，才能在程序中使用它。然后使用将列表追加到字典中。

## 蟒蛇 3

```py
from collections import defaultdict

Details = defaultdict(list)
Details["Country"].append("India")
print(Details)
```

**输出:**

```py
defaultdict(<class 'list'>, {'Country': ['India']})
```

由于 append 只接受一个参数，要插入另一个参数，请重复 append 方法。

## 蟒蛇 3

```py
from collections import defaultdict

Details = defaultdict(list)
Details["Country"].append("India")
Details["Country"].append("Pakistan")
print(Details)
```

**输出:**

```py
defaultdict(<class 'list'>, {'Country': ['India', 'Pakistan']})
```

## 方法四:使用[更新()](https://www.geeksforgeeks.org/python-dictionary-update-method/)功能

我们将使用 update 函数向字典中添加一个新列表。您可以使用 update()函数将字典嵌入到另一个字典中。

## 蟒蛇 3

```py
Details = {}
Details["Age"] = []
Details.update({"Age": [18, 20, 25, 29, 30]})
print(Details)
```

**输出:**

```py
{'Age': [18, 20, 25, 29, 30]}
```

## 方法 5:将列表直接添加到字典中

您可以使用 dict()函数将列表转换为 python 字典中某个键的值。

## 蟒蛇 3

```py
Values = [18, 20, 25, 29, 30]
Details = dict({"Age": Values})
print(Details)
```

**输出:**

```py
{'Age': [18, 20, 25, 29, 30]}
```