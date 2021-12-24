# Python 中的数据类|简介

> 原文:[https://www . geesforgeks . org/data-class-in-python-an-introduction/](https://www.geeksforgeeks.org/data-classes-in-python-an-introduction/)

**数据类模块**是 Python 3.7 中引入的一个实用工具，用来制作专门用于存储数据的结构化类。这些类持有特定的属性和函数，专门处理数据及其表示。
***广泛使用的 Python3.6**
中的【数据类】**虽然该模块是在 Python3.7 中引入的，但也可以通过安装*数据类*库在 Python3.6 中使用。*** 

```
pip install dataclasses
```

数据类通过使用带有类的[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)来实现。属性在 python 中是使用类型提示声明的，本质上是在 Python 中为变量指定数据类型。

## 蟒蛇 3

```
# A basic Data Class

# Importing dataclass module
from dataclasses import dataclass

@dataclass
class GfgArticle():
    """A class for holding an article content"""

    # Attributes Declaration
    # using Type Hints

    title: str
    author: str
    language: str
    upvotes: int

# A DataClass object
article = GfgArticle("DataClasses",
                     "vibhu4agarwal",
                     "Python", 0)
print(article)
```