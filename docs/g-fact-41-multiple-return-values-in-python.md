# 在 Python 中返回多个值

> 原文:[https://www . geesforgeks . org/g-fact-41-python 中的多重返回值/](https://www.geeksforgeeks.org/g-fact-41-multiple-return-values-in-python/)

在 Python 中，我们可以从一个函数中返回多个值。以下是不同的方法

**1)** **使用对象:**这类似于 C/C++和 Java，我们可以创建一个类(在 C 中，struct)来保存多个值并返回该类的一个对象。

```
# A Python program to return multiple 
# values from a method using class
class Test:
    def __init__(self):
        self.str = "geeksforgeeks"
        self.x = 20   

# This function returns an object of Test
def fun():
    return Test()

# Driver code to test above method
t = fun() 
print(t.str)
print(t.x)
```

输出:

```
geeksforgeeks
20
```

下面是一些改变 C++/Java 世界的有趣方法。

**2)使用元组:**元组是以逗号分隔的项目序列。它是在有或没有()的情况下创建的。元组是不可变的。元组和列表详见[本](http://geeksquiz.com/python-set-3-strings-lists-tuples-iterations/)。

```
# A Python program to return multiple 
# values from a method using tuple

# This function returns a tuple
def fun():
    str = "geeksforgeeks"
    x   = 20
    return str, x;  # Return tuple, we could also
                    # write (str, x)

# Driver code to test above method
str, x = fun() # Assign returned tuple
print(str)
print(x)
```

输出:

```
geeksforgeeks
20
```

**3)使用列表:**列表就像使用方括号创建的项目数组。它们不同于数组，因为它们可以包含不同类型的项。列表不同于元组，因为它们是可变的。

```
# A Python program to return multiple 
# values from a method using list

# This function returns a list
def fun():
    str = "geeksforgeeks"
    x = 20   
    return [str, x];  

# Driver code to test above method
list = fun() 
print(list)
```

输出:

```
['geeksforgeeks', 20]
```

**4)使用字典:**字典类似于其他语言中的哈希或映射。字典详见[本](http://geeksquiz.com/python-set-4-dictionary-keywords-python/)。

```
# A Python program to return multiple 
# values from a method using dictionary

# This function returns a dictionary
def fun():
    d = dict(); 
    d['str'] = "GeeksforGeeks"
    d['x']   = 20
    return d

# Driver code to test above method
d = fun() 
print(d)
```

输出:

```
{'x': 20, 'str': 'GeeksforGeeks'}
```

**5)使用数据类(Python 3.7+):** 在 Python 3.7 及以上版本中，数据类可以用来返回带有自动添加的唯一方法的类。数据类模块有一个装饰器和函数，用于在用户定义的类中自动添加生成的特殊方法，如 __init__()和 __repr__()等。

```
from dataclasses import dataclass

@dataclass
class Book_list:
    name: str
    perunit_cost: float
    quantity_available: int = 0

    # function to calculate total cost    
    def total_cost(self) -> float:
        return self.perunit_cost * self.quantity_available

book = Book_list("Introduction to programming.", 300, 3)
x = book.total_cost()

# print the total cost
# of the book
print(x)

# print book details
print(book)

# 900
Book_list(name='Python programming.',
          perunit_cost=200,
          quantity_available=3)
```

输出:

```
900
Book_list(name='Introduction to programming.', perunit_cost=300, quantity_available=3)
Book_list(name='Python programming.', perunit_cost=200, quantity_available=3)
```

**参考:**
[http://stackoverflow . com/questions/354883/如何返回 python 中的多个值](http://stackoverflow.com/questions/354883/how-do-you-return-multiple-values-in-python)

本文由 **Shubham Agrawal** 供稿。如果你喜欢极客博客并想投稿，你也可以写一篇文章并把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果您发现任何不正确的地方，或者您想分享更多关于上面讨论的主题的信息，请写评论