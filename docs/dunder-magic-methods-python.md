# Python 中的 Dunder 或魔法方法

> 原文:[https://www.geeksforgeeks.org/dunder-magic-methods-python/](https://www.geeksforgeeks.org/dunder-magic-methods-python/)

[Python](https://www.geeksforgeeks.org/python-programming-language/) 中的 Dunder 或 magic 方法是在方法名中有两个前缀和后缀下划线的方法。邓德在这里的意思是“双下划线”。这些通常用于运算符重载。魔术方法的几个例子是:`__init__, __add__, __len__, __repr__`等。

当创建一个类的实例时，初始化的`__init__`方法被调用，没有任何调用，就像某些其他编程语言中的构造函数，如 C++、Java、C#、PHP 等。这些方法是我们不用任何显式类型转换就可以用‘+’运算符添加两个字符串的原因。

这里有一个简单的实现:

```py
# declare our own string class
class String:

    # magic method to initiate object
    def __init__(self, string):
        self.string = string

# Driver Code
if __name__ == '__main__':

    # object creation
    string1 = String('Hello')

    # print object location
    print(string1)
```

**输出:**

```py
<__main__.String object at 0x7fe992215390>

```

上面的代码片段只打印字符串对象的内存地址。让我们添加一个`__repr__`方法来表示我们的对象。

```py
# declare our own string class
class String:

    # magic method to initiate object
    def __init__(self, string):
        self.string = string

    # print our string object
    def __repr__(self):
        return 'Object: {}'.format(self.string)

# Driver Code
if __name__ == '__main__':

    # object creation
    string1 = String('Hello')

    # print object location
    print(string1)
```

**输出:**

```py
Object: Hello

```

**如果我们试图给它加上一个字符串:**

```py
# declare our own string class
class String:

    # magic method to initiate object
    def __init__(self, string):
        self.string = string

    # print our string object
    def __repr__(self):
        return 'Object: {}'.format(self.string)

# Driver Code
if __name__ == '__main__':

    # object creation
    string1 = String('Hello')

    # concatenate String object and a string
    print(string1 +' world')
```

**输出:**

```py
TypeError: unsupported operand type(s) for +: 'String' and 'str'

```

现在将`__add__`方法添加到字符串类中:

```py
# declare our own string class
class String:

    # magic method to initiate object
    def __init__(self, string):
        self.string = string 

    # print our string object
    def __repr__(self):
        return 'Object: {}'.format(self.string)

    def __add__(self, other):
        return self.string + other

# Driver Code
if __name__ == '__main__':

    # object creation
    string1 = String('Hello')

    # concatenate String object and a string
    print(string1 +' Geeks')
```

输出:

```py
Hello Geeks

```

**参考:**[docs.python.org](https://docs.python.org/3/reference/datamodel.html#basic-customization)。