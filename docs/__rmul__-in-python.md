# --【python 中的 rml _ _ t1】

> 原文:[https://www.geeksforgeeks.org/__rmul__-in-python/](https://www.geeksforgeeks.org/__rmul__-in-python/)

对于每个操作符符号，都有一个底层机制。这种底层机制是一种特殊的方法，将在操作符操作期间调用。这个特殊的方法叫做 **[神奇的方法](https://www.geeksforgeeks.org/dunder-magic-methods-python/)** 。对于每一个算术计算，如+、-、*、/，我们需要 2 个操作数来执行运算符功能。

**示例:**

```py
‘+’ ? ‘__add__’ method
‘_’ ? ‘__sub__’ method
‘*’ ? ‘__mul__’ method
```

由于本文仅限于乘法功能，我们将在这里看到乘法过程。为了执行乘法功能，我们必须将运算符符号绑定到左/右操作数。之前，去`__rmul__` 方法，我们会看到关于`__mul__`方法，帮助我们形象地理解乘法功能。

## __mul__()

我们来看一个表达式`x*y`，其中 x 是类 A 的一个实例。要执行`__mul__`方法，操作符查看左操作数(x)的类中 __mul__ 的存在，即操作符(*)将检查类 A 中是否存在“`__mul__`”方法。如果有`__mul__`方法，就叫`x.__mul__(y)`。否则，它将抛出“**类型错误:不支持的操作数**”错误消息。

**例 1:**

```py
class Foo(object):

    def __init__(self, val):
        self.val = val

    def __str__(self):
        return "Foo [% s]" % self.val

class Bar(object):

    def __init__(self, val):
        self.val = val

    def __str__(self):
        return "Bar [% s]" % self.val

# Driver Code
f = Foo(5)
b = Bar(6)
print(f * b)
```

**输出:**

```py
TypeError, unsupported operand type(s) for *: 'Foo' and 'Bar'
```

在上面的例子中，第一个操作数是 f，它的类是 Foo()。由于 Foo()没有`__mul__`方法，所以不懂乘法。因此，它将显示类型错误消息。如果我们检查另一个类 Bar()，即使它没有`__mul__`方法。所以，即使我们把乘法反向为(b*f)，它也会抛出同样的错误

**示例 2:** 让我们在 Foo 类中添加 __mul__ 方法。

```py
class Foo(object):

    def __init__(self, val):
        self.val = val

    def __mul__(self, other):
        return Foo(self.val * other.val)

    def __str__(self):
        return "Foo [% s]" % self.val

class Bar(object):

    def __init__(self, val):
        self.val = val

    def __str__(self):
        return "Bar [% s]" % self.val

# Driver Code
f = Foo(5)
b = Bar(6)
print(f * b)
```

**输出:**

```py
Foo 30
```

如前所述，默认情况下，运算符会查看左操作数的类，并在这里找到 __mul__ 方法。现在它知道该怎么做了，结果是 30 `f.__mul__(b) = 5.__mul__(6)`。如果我们将乘法反向为(b*f)，它会再次抛出问题，因为它会查看没有任何`__mul__`方法的左操作数类(Bar())。`b.__mul__(f)`威尔抛出问题，因为 b 级吧()没有`__mul__`方法。

## __rmul__

`__mul__`和`__rmul__`的一个细微差别是，运算符在左操作数中查找`__mul__`，在右操作数中查找`__rmul__`。例如，x*y. Operator 在 y 的类定义中查找`__rmul__`方法。如果找到`__rmul__`方法，会显示结果，否则抛出**类型错误信息**

**例 1:** 我们以上面的例子为例，稍加修改。

```py
class Foo(object):

    def __init__(self, val):
        self.val = val

    def __str__(self):
        return "Foo [% s]" % self.val

class Bar(object):

    def __init__(self, val):
        self.val = val

    def __rmul__(self, other):
        return Bar(self.val * other.val)

    def __str__(self):
        return "Bar [% s]" % self.val

# Driver code
f = Foo(5)
b = Bar(6)

print(f * b)
```

**输出:**

```py
Bar 30
```

在上面的例子中，它假设 f*b 为`b.__rmul__(f)`，因为`__rmul__`方法存在于实例 b 的 Bar()类中。符号将是`f.__rmul__(b)`。如果没有`__rmul__`方法，它就无法理解要标注什么，并抛出 TypeError 消息。'

这些类型的运算符需要 2 个操作数，默认情况下将同时携带`__mul__`和`__rmul__`方法。要执行正乘法和反乘法，请参见下面的示例。

**例 2:**

```py
class Foo(object):

    def __init__(self, val):
        self.val = val

    def __str__(self):
        return "Foo [% s]" % self.val

class Bar(object):

    def __init__(self, val):
        self.val = val

    def __rmul__(self, other):
        return Bar(self.val * other.val)

    def __mul__(self, other):
        return self.__rmul__(other)

    def __str__(self):
        return "Bar [% s]" % self.val

# Driver Code
f = Foo(5)
b = Bar(6)

print(b * f)
print(f * b)
```

**输出:**

```py
Bar [30]
Bar [30]
```