# Python 中类方法 vs 静态方法

> 原文:[https://www . geesforgeks . org/class-method-vs-static-method-python/](https://www.geeksforgeeks.org/class-method-vs-static-method-python/)

### **类法**

@classmethod 装饰器是一个内置的[函数装饰器](https://www.geeksforgeeks.org/function-decorators-in-python-set-1-introduction/)，它是一个在您的函数被定义之后得到评估的表达式。评估的结果会影响您的函数定义。
类方法接收类作为隐式的第一个参数，就像实例方法接收实例
**语法:**

```
class C(object):
 @classmethod
 def fun(cls, arg1, arg2, ...):
       ....
fun: function that needs to be converted into a class method
returns: a class method for function.
```

*   类方法是绑定到类而不是类的对象的方法。
*   他们可以访问类的状态，因为它采用指向类而不是对象实例的类参数。
*   它可以修改适用于该类所有实例的类状态。例如，它可以修改适用于所有实例的类变量。

### **静法**

静态方法不接收隐式的第一个参数。

**语法:**

```
class C(object):
 @staticmethod
 def fun(arg1, arg2, ...):
 ...
returns: a static method for function fun.
```

*   静态方法也是绑定到类而不是类的对象的方法。
*   静态方法不能访问或修改类状态。
*   它存在于类中，因为方法存在于类中是有意义的。

### **类方法 vs 静态方法**

*   类方法将 cls 作为第一个参数，而静态方法不需要特定的参数。
*   类方法可以访问或修改类状态，而静态方法不能访问或修改它。
*   一般来说，静态方法对类状态一无所知。它们是实用类型的方法，采用一些参数并处理这些参数。另一方面，类方法必须有类作为参数。
*   我们在 python 中使用@classmethod decorator 创建一个类方法，在 python 中使用@staticmethod decorator 创建一个静态方法。

### **什么时候用什么？**

*   我们通常使用类方法来创建工厂方法。工厂方法为不同的用例返回类对象(类似于构造函数)。
*   我们通常使用静态方法来创建实用函数。

### **如何定义类方法和静态方法？**

要在 python 中定义一个类方法，我们使用@classmethod decorator，要定义一个静态方法，我们使用@staticmethod decorator。
我们来看一个例子，了解两者的区别。假设我们想创建一个类 Person。现在，python 不像 C++或 Java 那样支持方法重载，所以我们使用类方法来创建工厂方法。在下面的例子中，我们使用一个类方法从出生年份创建一个 person 对象。
如上所述，我们使用静态方法来创建效用函数。在下面的例子中，我们使用静态方法来检查一个人是否是成年人。

**实施**

## 蟒蛇 3

```
# Python program to demonstrate
# use of class method and static method.
from datetime import date

class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age

    # a class method to create a Person object by birth year.
    @classmethod
    def fromBirthYear(cls, name, year):
        return cls(name, date.today().year - year)

    # a static method to check if a Person is adult or not.
    @staticmethod
    def isAdult(age):
        return age > 18

person1 = Person('mayank', 21)
person2 = Person.fromBirthYear('mayank', 1996)

print (person1.age)
print (person2.age)

# print the result
print (Person.isAdult(22))
```

**输出:**

```
21
25
True
```

本文由 **Mayank Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。