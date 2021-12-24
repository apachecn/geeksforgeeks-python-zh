# Python 中的动态属性

> 原文:[https://www.geeksforgeeks.org/dynamic-attributes-in-python/](https://www.geeksforgeeks.org/dynamic-attributes-in-python/)

[Python 中的**动态属性**是在创建对象或实例后，在运行时定义的属性的术语。在 Python 中，我们调用所有函数，方法也作为一个对象。因此，您可以在 Python 中为几乎任何东西定义一个动态实例属性。考虑下面的例子，以便更好地理解这个主题。](https://www.geeksforgeeks.org/python-programming-language/)

**例 1:**

```py
class GFG:
    None

def value():
    return 10

# Driver Code
g = GFG()

# Dynamic attribute of a
# class object
g.d1 = value

# Dynamic attribute of a 
# function
value.d1 = "Geeks"

print(value.d1)
print(g.d1() == value())
```

**输出:**

```py
Geeks
True
```

现在，上面的程序似乎有些混乱，但让我们试着理解一下。首先我们来看对象，g 和 value(函数在 Python 中也被认为是对象)是两个对象。这里，两个对象的动态属性都是“d1”。这是在运行时定义的，而不是像静态属性那样在编译时定义的。

**注意:**类“GFG”和该类的所有其他对象或实例都不知道属性“d1”。它只为实例“g”定义。

**例 2:**

```py
class GFG:

    employee = True

# Driver Code
e1 = GFG()
e2 = GFG()

e1.employee = False
e2.name = "Nikhil"

print(e1.employee)
print(e2.employee)
print(e2.name)

# this will raise an error 
# as name is a dynamic attribute
# created only for the e2 object
print(e1.name)
```

**输出:**

```py
False
True
Nikhil
```

```py
Traceback (most recent call last):
  File "/home/fbcfcf668619b24bb8ace68e3c400bc6.py", line 19, in 
    print(e1.name)
AttributeError: 'GFG' object has no attribute 'name'
```