# Python 中的条件继承

> 原文:[https://www . geeksforgeeks . org/python 中的条件继承/](https://www.geeksforgeeks.org/conditional-inheritance-in-python/)

大多数情况下，在给定一个条件的情况下，我们需要决定一个特定的班级是否应该继承一个班级，例如，给定一个人，如果他/她有资格被大学录取，那么他们应该是学生，否则他们不应该是学生。

让我们考虑一个例子，其中给定一个条件，我们希望一个类(比如 C)从类 A 或类 B 动态继承。我们需要创建两个不同的类 C_A 和 C_B，它们分别从 A 和 B 继承。然而，如果条件继承是继承或者不是基于一个条件，那么我们可以使用不同的方法，如下所述

**例 1:两个类之间的条件继承:**

创建两个类 C_A 和 C_B，并根据条件返回各自的类对象。

## 蟒蛇 3

```
class A(object): 
    def __init__(self, x): 
        self.x = x

    def getX(self): 
        return self.X

class B(object): 
    def __init__(self, x, y): 
        self.x = x
        self.y = y
    def getSum(self): 
        return self.X + self.y

# inherits from A  
class C_A(A):
    def isA(self):
        return True

    def isB(self):
        return False

# inherits from B  
class C_B(B):
    def isA(self):
        return False

    def isB(self):
        return True

# return required Object of C based on cond  
def getC(cond):
    if cond:
        return C_A(1)
    else:
        return C_B(1,2)

# Object of C_A
ca = getC(True)
print(ca.isA())
print(ca.isB())  

# Object of C_B  
cb = getC(False)
print(cb.isA())
print(cb.isB())
```

**输出:**

```
True
False
False
True
```

**例 2:继承或不继承 A:**

方法是在声明给定类 C 继承的类时使用条件语句。下面的代码执行并返回真

## 蟒蛇 3

```
class A(object): 
    def __init__(self, x): 
        self.x = x

    def getX(self): 
        return self.X

# Based on condition C inherits 
# from A or it inherits from 
# object i.e. does not inherit A
cond = True  

# inherits from A or B
class C(A if cond else object):
    def isA(self):
        return True

# Object of C_A
ca = C(1)
print(ca.isA())
```

**输出:**

```
True
```

**示例 3:** 下面的代码不会运行，因为 C 没有从 A 继承，因此有一个不接受任何参数的默认构造函数

## 蟒蛇 3

```
class A(object): 
    def __init__(self, x): 
        self.x = x

    def getX(self): 
        return self.X

# Based on condition C inherits from
# A or it inherits from object i.e.
# does not inherit A
cond = False

## inherits from A or B
class C(A if cond else object):
    def isA(self):
        return True

# Object of C_A
ca = C(1)
print(ca.isA())
```

**输出:**

> TypeError 回溯(最近一次调用最后一次)
> <ipython-input-16-f0efc5 A 814d 9>在<模块>
> 中**17**
> **18**# C _ A 的对象
> —>19 ca = C(1)
> **20**打印(ca.isA())
> **21**
> 
> 类型错误:对象()没有参数