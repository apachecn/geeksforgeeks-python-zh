# Python 中的运算符重载

> 原文:[https://www . geesforgeks . org/operator-python 中的重载/](https://www.geeksforgeeks.org/operator-overloading-in-python/)

运算符重载意味着给出超出其预定义操作含义的扩展含义。例如，运算符+用于添加两个整数，连接两个字符串并合并两个列表。这是可以实现的，因为“+”运算符被 int 类和 str 类重载。您可能已经注意到，相同的内置运算符或函数对不同类的对象显示不同的行为，这被称为*运算符重载*。

## 蟒蛇 3

```
# Python program to show use of
# + operator for different purposes.

print(1 + 2)

# concatenate two strings
print("Geeks"+"For")

# Product two numbers
print(3 * 4)

# Repeat the String
print("Geeks"*4)
```

**输出:**

```
3
GeeksFor
12
GeeksGeeksGeeksGeeks
```

**Python 中如何重载操作符？**
考虑我们有两个对象，它们是一个类(用户定义的数据类型)的物理表示，我们必须用二进制“+”运算符添加两个对象，这会抛出一个错误，因为编译器不知道如何添加两个对象。所以我们为一个操作符定义了一个方法，这个过程叫做操作符重载。我们可以重载所有现有的操作符，但不能创建新的操作符。为了执行运算符重载，Python 提供了一些特殊的函数或神奇的函数，当它与特定的运算符相关联时，会自动调用这些函数。例如，当我们使用+运算符时，会自动调用 magic 方法 __add__ 其中定义了+运算符的操作。
**Python 中重载二进制+运算符:**
当我们在用户定义的数据类型上使用运算符时，会自动调用与该运算符相关联的特殊函数或神奇函数。改变运算符的行为就像改变方法或函数的行为一样简单。您在类中定义方法，操作符根据方法中定义的行为工作。当我们使用+运算符时，会自动调用 magic 方法 __add__ 其中定义了+运算符的操作。通过改变这个神奇方法的代码，我们可以给+运算符赋予额外的意义。
**代码 1:**

## 蟒蛇 3

```
# Python Program illustrate how
# to overload an binary + operator

class A:
    def __init__(self, a):
        self.a = a

    # adding two objects
    def __add__(self, o):
        return self.a + o.a
ob1 = A(1)
ob2 = A(2)
ob3 = A("Geeks")
ob4 = A("For")

print(ob1 + ob2)
print(ob3 + ob4)
```

**输出:**

```
3
GeeksFor
```

**代码 2:**

## 蟒蛇 3

```
# Python Program to perform addition
# of two complex numbers using binary
# + operator overloading.

class complex:
    def __init__(self, a, b):
        self.a = a
        self.b = b

     # adding two objects
    def __add__(self, other):
        return self.a + other.a, self.b + other.b

Ob1 = complex(1, 2)
Ob2 = complex(2, 3)
Ob3 = Ob1 + Ob2
print(Ob3)
```

**输出:**

```
(3, 5)
```

**Python 中重载比较运算符:**

## 蟒蛇 3

```
# Python program to overload
# a comparison operators

class A:
    def __init__(self, a):
        self.a = a
    def __gt__(self, other):
        if(self.a>other.a):
            return True
        else:
            return False
ob1 = A(2)
ob2 = A(3)
if(ob1>ob2):
    print("ob1 is greater than ob2")
else:
    print("ob2 is greater than ob1")
```

**输出:**

```
ob2 is greater than ob1
```

**重载相等小于运算符:**

## 蟒蛇 3

```
# Python program to overload equality
# and less than operators

class A:
    def __init__(self, a):
        self.a = a
    def __lt__(self, other):
        if(self.a<other.a):
            return "ob1 is lessthan ob2"
        else:
            return "ob2 is less than ob1"
    def __eq__(self, other):
        if(self.a == other.a):
            return "Both are equal"
        else:
            return "Not equal"

ob1 = A(2)
ob2 = A(3)
print(ob1 < ob2)

ob3 = A(4)
ob4 = A(4)
print(ob1 == ob2)
```

**输出:**

```
ob1 is lessthan ob2
Not equal
```

#### Python 魔法方法或运算符重载的特殊函数

#### [二进制运算符](https://www.geeksforgeeks.org/basic-operators-python/):

<figure class="table">

| 操作员 | 魔术方法 |
| **+** | __ 添加 _ _(自身、其他) |
| **–** | __sub__(自身、其他) |
| ***** | __mul__(自身、其他) |
| **/** | __truediv__(自我，其他) |
| **//** | __floordiv__(自身、其他) |
| **%** | __mod__(自身、其他) |
| ****** | __pow__(自身，其他) |
| >> | __rshift__(自身、其他) |
| << | _ _ lshift _ _(自我，其他) |
| & | __ 和 _ _(自身、其他) |
| &#124; | __ 或 _ _(自身、其他) |
| ^ | __xor__(自身，其他) |

</figure>

#### 比较运算符:

<figure class="table">

| 操作员 | 魔术方法 |
| **<** | __LT__(自我，其他) |
| **>** | __GT__(自我，其他) |
| **< =** | __LE__(自我，其他) |
| **> =** | __ 通用电气 _ _(自身、其他) |
| **==** | __EQ__(自我，其他) |
| **！=** | __NE__(自我，其他) |

</figure>

#### 分配运算符:

<figure class="table">

| 操作员 | 魔术方法 |
| **-=** | __ISUB__(自我，其他) |
| **+=** | __IADD__(自我，其他) |
| ***=** | __IMUL__(自身、其他) |
| **/=** | __IDIV__(自我，其他) |
| **//=** | __IFLOORDIV__(自我，其他) |
| **%=** | __IMOD__(自我，其他) |
| ****=** | __IPOW__(自我，其他) |
| **> > =** | __IRSHIFT__(自我，其他) |
| **< < =** | __ILSHIFT__(自我，其他) |
| **& =** | __ 和 _ _(自身，其他) |
| **&#124;=** | __IOR__(自我，其他) |
| **^=** | __IXOR__(自我，其他) |

</figure>

#### 一元运算符:

<figure class="table">

| 操作员 | 魔术方法 |
| **–** | __ 否定 _ _(自我，其他) |
| **+** | __ 位置 _ _(自身、其他) |
| **~** | __ 反转 _ _(自身，其他) |

</figure>