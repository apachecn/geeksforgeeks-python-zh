# _ _ _ _ _ _ _()python

> 原文:[https://www.geeksforgeeks.org/__getitem__-in-python/](https://www.geeksforgeeks.org/__getitem__-in-python/)

在 Python 中，一切都是对象。场景后面的这些对象上有很多‘普通’的系统调用方法，程序员是看不到的。这里出现了所谓的[魔法方法](https://www.geeksforgeeks.org/dunder-magic-methods-python/)。python 中的 Magic 方法是我们运行任何普通 python 代码时都会调用的特殊方法。为了与普通函数区分开来，它们有环绕的双下划线。

如果我们想添加 a 和 b，我们编写以下语法:

```
c = a + b

```

内部称为:

```
c = a.__add__(b)

```

`__getitem__()`是 Python 中的一个神奇的方法，当在类中使用时，允许它的实例使用`[]`(索引器)运算符。假设 x 是这个类的一个实例，那么`x[i]`大致相当于`type(x).__getitem__(x, i)`。

方法`__getitem__(self, key)`使用符号`self[key]`定义访问项目时的行为。这也是可变和不可变容器协议的一部分。

**例:**

```
# Code to demonstrate use
# of __getitem__() in python

class Test(object):

    # This function prints the type
    # of the object passed as well 
    # as the object item
    def __getitem__(self, items):
        print (type(items), items)

# Driver code
test = Test()
test[5]
test[5:65:5]
test['GeeksforGeeks']
test[1, 'x', 10.0]
test['a':'z':2]
test[object()]
```

**输出:**

```
<class 'int'> 5
<class 'slice'> slice(5, 65, 5)
<class 'str'> GeeksforGeeks
<class 'tuple'> (1, 'x', 10.0)
<class 'slice'> slice('a', 'z', 2)
<class 'object'> <object object at 0x7f75bcd6d0a0>

```

与其他一些语言不同，Python 基本上允许您将任何对象传递给索引器。你可能会惊讶`test[1, 'x', 10.0]`居然会解析。对于 Python 解释器来说，这个表达式相当于这样:`test.__getitem__((1, 'x', 10.0))`。如您所见，1，' x '，10.0 部分被隐式解析为元组。`test[5:65:5]`表达式使用了 Python 的切片语法。相当于这个表达式:test[slice(5，65，5)]。

`__getitem__`魔术方法通常用于列表索引、字典查找或访问值的范围。考虑到它的多功能性，它可能是 Python 中使用最少的神奇方法之一。