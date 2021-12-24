# 使用 Magic 或 Dunder 方法自定义您的 Python 类

> 原文:[https://www . geeksforgeeks . org/customize-your-python-class-with-magic-or-dunder-methods/](https://www.geeksforgeeks.org/customize-your-python-class-with-magic-or-dunder-methods/)

神奇的方法确保了一致的数据模型，它保留了内置类的继承特性，同时提供了定制的类行为。这些方法可以丰富类的设计，增强语言的可读性。
所以，在本文中，我们将看到如何利用神奇的方法，它是如何工作的，以及 Python 中可用的神奇方法。让我们来看看每个部分:

*   [魔术方法语法](#syntax)
*   [常用魔法方法](#common)
*   [二元运算符的神奇方法](#binary)
*   [一元运算符的神奇方法](#unary)
*   [其他一些神奇的方法](#few)

## 魔术方法语法

两边用两个下划线包装的方法称为魔术方法。神奇方法背后的动机是重载 Python 的内置方法及其操作符。这里，_ 语法防止程序员为自定义方法定义相同的名称。每种神奇的方法都有它的用途。让我们考虑一个检查等价性的例子。
**例:**

## 蟒蛇 3

```py
class EquivalenceClass(object):
    def __eq__(self, other):
        return type(self) == type(other)

print(EquivalenceClass() == EquivalenceClass())
print(EquivalenceClass() == 'MyClass')
```

**输出**T2】

```py
True
False
```

__eq__ 方法使用两个参数——self 和 object——来检查相等性。重要的是要理解，当使用==运算符比较两个对象时，会调用 __eq__ 方法。让我们来看看 python 中一些常见的神奇方法。

## 常见的魔术方法

在 Python 中，我们有各种各样的神奇方法——每种方法都有自己的用途。下面我们就来梳理一下，几种常见的魔法方法:

*   创造
*   破坏
*   类型变换
*   比较

### 创造

在创建过程中纠缠在一起的魔术方法是在创建类实例时执行的。关联的两个神奇方法是 __init__ 和 __new__ 方法。

#### [__init__ 方法](https://www.geeksforgeeks.org/__init__-in-python/)

对象的 [__init__](https://www.geeksforgeeks.org/__init__-in-python/) 方法在实例创建后立即执行。这里，该方法采用一个位置参数(self)和任意数量的可选参数或关键字参数。我们来看一个简单的例子:
**例子:**

## 蟒蛇 3

```py
class InitClass(object):
    def __init__(self):
        print('Executing the __init__ method.')

ic = InitClass()
```

**输出**T2】

```py
Executing the __init__ method.
```

这里，需要注意的要点是，您没有调用 __init__ 方法。相反，Python 解释器在对象实例化时进行调用。让我们考虑一个例子，它采用一个可选的参数:

## 蟒蛇 3

```py
class Square(object):
    def __init__(self, number = 2):
        self._number = number

    def square(self):
        return self._number**2

s = Square()
print('Number: % i' % s._number)
print('Square: % i' % s.square())
```

**输出**T2】

```py
Number: 2
Square: 4
```

这里我们可以注意到，缺省值(2)由 __init__ 方法在没有可选参数的情况下使用。让我们检查一下 __init__ 方法的一些事实:

*   __init__ 方法向对象提供初始数据，而不是创建对象。

*   它只返回无；返回“无”以外的值会引发类型错误。

*   它定制类的实例化。

接下来，我们将继续使用 __new__ 方法。

#### [__ 新 _ _ 法](https://www.geeksforgeeks.org/__new__-in-python/)

[__new__](https://www.geeksforgeeks.org/__new__-in-python/) 方法创建并返回一个类的实例。__new__ 方法的主要参数是必须实例化的类，其余参数是在类调用期间提到的参数。让我们通过一个例子来探讨:
**例子:**

## 蟒蛇 3

```py
class Students(object):
    def __init__(self, idNo, grade):
        self._idNo = idNo
        self._grade = grade

    def __new__(cls, idNo, grade):
        print("Creating Instance")
        instance = super(Students, cls).__new__(cls)
        if 5 <= grade <= 10:
            return instance
        else:
            return None

    def __str__(self):
        return '{0}({1})'.format(self.__class__.__name__, self.__dict__)

stud1 = Students(1, 7)
print(stud1)

stud2 = Students(2, 12)
print(stud2)
```

**输出**T2】

```py

Creating Instance
Students({'_idNo': 1, '_grade': 7})
Creating Instance
None
```

在大多数情况下，我们不需要定义 __new__ 方法。如果我们选择 __new__ 方法实现，那么引用超类是必须的。另一个需要注意的要点是，只有当 __new__ 方法返回同一个类的实例时，实例化类 get 的 __init__ 方法才会执行。

### 破坏

#### [__del__ 法](https://www.geeksforgeeks.org/python-del-to-delete-objects/)

__del__ 方法在销毁类的实例时被调用——通过垃圾收集器直接删除或恢复内存。让我们检查下面的代码:

## 蟒蛇 3

```py
class MyClass(object):
    def __del__(self):
        print('Destroyed')

MyClass()
'Immutable String - not assigned to a variable'
```

**输出**T2】

```py
Destroyed
```

当我们创建一个对象而不将它们赋给一个变量时会发生什么？垃圾收集器将保留对象的记录，这些记录没有被引用到变量，并在另一个程序语句执行时删除它。在这里，我们创建了一个 MyClass 的对象，但没有将其分配给一个变量。在执行程序语句(不可变字符串–未分配给变量)时，垃圾收集器会销毁 MyClass 对象。
同样的情况发生，当我们直接删除对象；但是在这里删除会立即发生。试试下面的代码。

x = MyClass()
第十部分

### 类型变换

类型转换是指一种数据类型到另一种数据类型的转换；Python 提供了几种神奇的方法来处理转换。

*   __str__ 方法
*   __int__ 和 __float__ 和 __complex__ 方法
*   __bool__ 方法

#### __str__ 方法

__str__ 方法需要一个位置参数——self——并返回一个字符串。当对象被传递给 str()构造函数时调用它。让我们考虑一个例子:

## 蟒蛇 3

```py
class MyString(object):
    def __str__(self):
        return 'My String !'

print(str(MyString()))
```

**输出**T2】

```py
My String!
```

让我们看一下调用 __str__ 方法的另一种情况。场景是在格式字符串中使用%s，这又调用 __str__ 方法。

## 蟒蛇 3

```py
class HelloClass(object):
    def __str__(self):
        return 'George'

print('Hello, % s' % HelloClass())
```

**输出**T2】

```py
Hello, George
```

#### __int__ 和 __float__ 和 __complex__ 方法

__int__ 方法在调用 int 构造函数时执行，并返回一个 int；它将复杂的对象转换成基本的 int 类型。同样，__float__ 和 _ complex _ _ 方法在将对象分别传递给 float 和 complex 构造函数时执行。

#### __bool__ 方法

python 中的 __bool__ magic 方法接受一个位置参数，并返回 true 或 false。它的目的是检查对象是真还是假，或者显式转换为布尔值。

### 比较

当我们检查等价性(==，！=)或关系( =)。python 中的每个操作符都被映射到其对应的魔法方法。

#### 二元等式

1. **__eq__ 方法**
当使用==运算符比较两个对象时，会执行 __eq__ 方法。它需要两个位置参数——自我和对象来检查等式。
大多数情况下，如果定义了左侧的对象，那么首先检查其等价性。我们来看一个例子:

## 蟒蛇 3

```py
class MyEquivalence(object):
    def __eq__(self, other):
        print('MyEquivalence:\n'
              '% r\n % r' %(self, other))
        return self is other

class YourEquivalence(object):
    def __eq__(self, other):
        print('Your Equivalence:\n'
              '% r\n % r' %(self, other))
        return self is other

eq1 = MyEquivalence()
eq2 = YourEquivalence()
# checking for equivalence where eq1 is at the left side
print(eq1 == eq2)
# checking for equivalence where eq2 is at the left side
print(eq2 == eq1)
```

**输出**T2】

```py
MyEquivalence:
<__main__.MyEquivalence object at 0x7fa1d38e16d8>
<__main__.YourEquivalence object at 0x7fa1d1ea37b8>
False
Your Equivalence:
<__main__.YourEquivalence object at 0x7fa1d1ea37b8>
<__main__.MyEquivalence object at 0x7fa1d38e16d8>
False
```

如果一个对象是另一个对象的直接子类，则排序规则不适用。让我们通过一个例子来检验一下:

## 蟒蛇 3

```py
class MyEquivalence(object):
    def __eq__(self, other):
        print('MyEquivalence:\n'
              '% r\n % r' %(self, other))
        return self is other

class MySubEquivalence(MyEquivalence):
    def __eq__(self, other):
        print('MySubEquivalence:\n'
              '% r\n % r' %(self, other))
        return self is other

eqMain = MyEquivalence()
eqSub = MySubEquivalence()

# eqMain at the right side
print(eqMain == eqSub)

# eqSub at the right side
print(eqSub == eqMain)
```

**输出**T2】

```py
MyEquivalence:
<__main__.MyEquivalence object at 0x7fa1d38e16d8>
<__main__.YourEquivalence object at 0x7fa1d1ea37b8>
False
Your Equivalence:
<__main__.YourEquivalence object at 0x7fa1d1ea37b8>
<__main__.MyEquivalence object at 0x7fa1d38e16d8>
False
```

2. **__ne__ 法**
该 __ne__ 魔法执行，当！=使用了运算符。在大多数情况下，我们不需要定义 __ne__ 方法；使用时！=运算符，python 解释器将执行 __eq__ 方法并反转结果。

#### 相对比较——lt _ _ _ & _ _ le _ _，gt _ _ & _ _ ge _ _ 方法

当< and <= operators are used, respectively.And, the __gt__ and __ge__ methods are invoked on using  >和> =运算符时，分别调用 __lt__ 和 __le__ 方法。然而，没有必要使用所有这 4 种方法；使用 __lt__ 和 __gt__ 方法就可以达到目的。只要考察以下几点，就能明白为什么我们不需要所有这些方法:
1。__ge__ 和 __le__ 方法可以分别替换为 __lt__ 和 __gt__ 方法的逆方法。
2。可以使用 __lt__ 和 __eq__ 方法的析取来代替 __le__ 方法，同样，对于 __ge__ 方法，也可以使用 __gt__ 和 __eq__ 方法。
我们来看看下面的例子。这里，我们将根据对象的创建时间对其进行比较。

## 蟒蛇 3

```py
import time
class ObjectCreationTime(object):
    def __init__(self, objName):
        self._created = time.time()
        self._objName = objName

    def __lt__(self, other):
        print('Creation Time:\n'
              '% s:% f\n % s:% f' %(self._objName, self._created,
                                 other._objName, other._created))
        return self._created < other._created

    def __gt__(self, other):
        print('Creation Time:\n'
              '% s:% f\n % s:% f' %(self._objName, self._created,
                                 other._objName, other._created))
        return self._created > other._created

obj1 = ObjectCreationTime('obj1')
obj2 = ObjectCreationTime('obj2')
print(obj1 < obj2)
print(obj1 > obj2)
```

**输出**T2】

```py
Creation Time:
obj1:1590679265.753279
obj2:1590679265.753280
True
Creation Time:
obj1:1590679265.753279
obj2:1590679265.753280
False
```

## 二元算子的魔术方法

让我们看看 python 为二进制运算符提供的 3 种神奇方法。

*   香草法
*   反向法
*   就地方法

### 香草法

考虑一个表达式，x+y；在普通方法中，这个表达式映射到 x.__add__(y)。
让我们考虑另一个表达式，y–x，这里，表达式映射到 y _ _ _ sub _ _(x)。同样，a * b 映射到 a.__mul__(b)，a / b 映射到 a.__truediv__(b)，依此类推。需要注意的一点是，左侧对象的方法被调用，并将右侧对象作为参数传递。在 x + y 的情况下，调用 x 的 __add__ 方法，并将 y 作为参数传递。让我们用一个例子来检验一下。

## 蟒蛇 3

```py
class Count(object):
    def __init__(self, count):
        self._count = count
    def __add__(self, other):
        total_count = self._count + other._count
        return Count(total_count)
    def __str__(self):
        return 'Count: % i' % self._count

c1 = Count(2)
c2 = Count(5)
c3 = c1 + c2
print(c3)
```

**输出**T2】

```py
Count: 7
```

### 反向法

在香草方法中，左侧对象的方法在执行二进制运算符时被调用。但是，如果左侧对象没有二元运算符映射的方法，则调用相反的方法；它检查要映射的右侧对象的方法。我们来看看下面的例子:

## 蟒蛇 3

```py
class Count(object):
    def __init__(self, count):
        self._count = count

    def __add__(self, other):
        total_count = self._count + other._count
        return Count(total_count)

    def __radd__(self, other):
        if other == 0:
            return self
        else:
            return self.__add__(other)

    def __str__(self):
        return 'Count:% i' % self._count

c2 = Count(2)
c3 = 0 + c2
print(c3)
```

**输出**T2】

```py
Count:2
```

由于 0 没有 __add__ 方法与之对应，python 解释器会调用 __radd__ 方法–C2。__radd__(0)。同样，如果没有定义 __sub__ 方法，它将调用 __rsub __。

### 就地方法

计算和赋值操作都是在使用就地方法时执行的。映射到就地方法的一些运算符是+=，-=，*=，等等。就地方法名称前面有 I。例如，语句 x += y 将映射到 x.__iadd__(y)等等。让我们来看看下面的例子:

## 蟒蛇 3

```py
class inPlace(object):
    def __init__(self, value):
        self._value = value
    def __iadd__(self, other):
        self._value = self._value + other._value
        return self._value
    def __str__(object):
        return self._value

inP1 = inPlace(5)
inP2 = inPlace(3)
inP1 += inP2
print(inP1)
```

**输出**T2】

```py
8
```

## 一元算子的魔术方法

*   __pos__ 方法
*   __neg__ 方法
*   __ 反转 _ _ 方法

### __pos__ 方法

使用+运算符调用 __pos__ 方法。我们已经看到+运算符也起二元运算符的作用。不用担心，python 解释器知道根据情况使用哪一个——一元还是二元。
_ _ pos _ _ 方法接受单个位置参数–self –,执行操作，并返回结果。我们通过一个例子来考察一下:

## 蟒蛇 3

```py
class unaryOp(object):
    def __init__(self, value):
        self._value = value
    def __pos__(self):
        print('__pos__ magic method')
        return(+self._value)

up = unaryOp(5)
print(+up)
```

**输出**T2】

```py
__pos__ magic method
5
```

### __neg__ 方法

使用–运算符调用 __neg__ 方法。这个操作符也充当二进制操作符，但是解释器根据情况决定映射哪个神奇的方法。__neg__ magic 方法接受单个位置参数 self –,进行运算并返回结果。我们来看看下面的例子:

## 蟒蛇 3

```py
class unaryOp(object):
    def __init__(self, value):
        self._value = value
    def __neg__(self):
        print('__neg__ magic method')
        return(-self._value)

up = unaryOp(5)
print(-up)
```

**输出**T2】

```py
__neg__ magic method
-5
```

### __ 反转 _ _ 方法

最后一个一元运算符是 __invert__ 方法，该方法使用~运算符调用。语句~x 相当于 x.__invert__()。让我们考虑一个例子:

## 蟒蛇 3

```py
class invertClass(object):
    def __init__(self, value):
        self._value = value
    def __invert__(self):
        return self._value[::-1]
    def __str__(self):
        return self._value

invrt = invertClass('Hello, George')
invertedValue = ~invrt
print(invertedValue)
```

**输出**T2】

```py
egroeG, olleH
```

## 其他一些神奇的方法

让我们讨论几个其他的神奇方法:

*   __len__ 方法
*   __repr__ 方法
*   __ 包含 _ _ 方法

### 重载 __len__ 方法

len()方法调用 __len__ magic 方法。它接受一个位置参数并返回对象的长度。让我们看看下面的代码:

## 蟒蛇 3

```py
class RectangleClass(object):
    def __init__(self, area, breadth):
        self._area = area
        self._breadth = breadth

    def __len__(self):
        return int(self._area / self._breadth)

rc = RectangleClass(90, 5)
print(len(rc))
```

**输出**T2】

```py
18
```

### __repr__ 方法的重要性

__repr__ magic 方法有助于在 Python 交互终端中表示一个对象。它需要一个位置论证——自我。
我们来看看，一个对象是如何在 Python 交互终端中不重载 __repr__ 方法来表示的。

## 蟒蛇 3

```py
class RectangleClass(object):
    def __init__(self, area, breadth):
        self._area = area
        self._breadth = breadth

    def __len__(self):
        return int(self._area / self._breadth)

## use python interactive terminal to check object representation.
RectangleClass(90, 5)
```

**输出**T2】

```py
<__main__.RectangleClass object at 0x7f9ecaae9710>
```

我们可以看到，它返回内存中对象的地址，这并没有那么有用。
让我们看看如何重载 __repr__ 方法来返回有用的对象表示。

## 蟒蛇 3

```py
class RectangleClass(object):
    def __init__(self, area, breadth):
        self._area = area
        self._breadth = breadth

    def __len__(self):
        return int(self._area / self._breadth)

    def __repr__(self):
        """object representation"""
        return 'RectangleClass(area =% d, breadth =% d)' %\
               (self._area, self._breadth)

RectangleClass(90, 5)  
RectangleClass(80, 4)  
```

**输出**T2】

```py
RectangleClass(area=90, breadth=5)
RectangleClass(area=80, breadth=4)
```

### __ 包含 _ _ 个魔术方法

当“in”表达式执行时，调用 __contains__ 方法。它接受两个位置参数——self 和 item——并返回 true。如果 item 存在或不存在，则返回 false。让我们通过一个例子来检验一下:

## 蟒蛇 3

```py
import datetime

class DateClass(object):
    def __init__(self, startDate, endDate):
        self.startDate = startDate
        self.endDate = endDate

    def __contains__(self, item):
        """ check whether a date is between the given range and
        return true or false"""
        return self.startDate <= item <= self.endDate

dtObj = DateClass(datetime.date(2019, 1, 1), datetime.date(2021, 12, 31))
result = datetime.date(2020, 6, 4) in dtObj
print("Whether (2020, 6, 4) is within the mentioned date range? ", result)

result = datetime.date(2022, 8, 2) in dtObj
print("Whether (2022, 8, 2) is within the mentioned date range? ", result)
```

**输出**T2】

```py
Whether (2020, 6, 4) is within the mentioned date range?  True
Whether (2022, 8, 2) is within the mentioned date range?  False
```

总结
因此，我们可以得出结论，魔术方法是一个一致的数据模型，可以定制类行为，增强可读性，而不会失去它们继承的特性。但是，在给出定制的特性之前，请确保定制是否是必要的。