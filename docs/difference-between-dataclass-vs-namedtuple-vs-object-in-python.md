# Python 中数据类与命名对象的区别

> 原文:[https://www . geesforgeks . org/data class-vs-named tuple-vs-object-in-python/](https://www.geeksforgeeks.org/difference-between-dataclass-vs-namedtuple-vs-object-in-python/)

[**数据类:**](https://www.geeksforgeeks.org/data-classes-in-python-an-introduction/) 数据类是一种用于存储数据的类，没有任何功能。这些数据类只是常规类，主要目的是存储状态和数据，而不知道其背后的约束和逻辑。每当您创建一个主要包含属性和某些属性的类来处理数据及其表示时。

**例:**

## 蟒 3

```
# Importing dataclass module 
from dataclasses import dataclass 

# Annotation
@dataclass

# Class with attributes
class GeeksArticle(): 
    """A class for holding an article content"""

    # Attributes Declaration 
    # using Type Hints 
    topic: str
    contributor: str
    language: str
    upvotes: int

# A DataClass object 
article = GeeksArticle("DataClasses", "nightfury1", "Python", 1)

print(article)
```