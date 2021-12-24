# Python 中的鸭子打字

> 原文:[https://www.geeksforgeeks.org/duck-typing-in-python/](https://www.geeksforgeeks.org/duck-typing-in-python/)

**鸭子打字**是动态语言中使用的[类型系统](https://www.geeksforgeeks.org/type-systemsdynamic-typing-static-typing-duck-typing/)。比如 Python、Perl、Ruby、PHP、Javascript 等。其中对象的类型或类不如它定义的方法重要。使用鸭打字，我们根本不检查类型。相反，我们检查给定方法或属性的存在。

鸭子打字这个名字来自于这样一句话:

> “如果它看起来像鸭子，叫起来像鸭子，那它就是鸭子”

**示例:**

```
# Python program to demonstrate
# duck typing

class Specialstring:
    def __len__(self):
        return 21

# Driver's code
if __name__ == "__main__":

    string = Specialstring()
    print(len(string))
```

**输出:**

```
21
```

在这种情况下，我们调用方法`len()`给出来自`__len__`方法的返回值。这里`__len__`方法定义了类`Specialstring`的属性

对象的类型本身并不重要，因为我们不在方法原型中声明参数。这意味着编译器不能进行类型检查。因此，真正重要的是对象在运行时是否具有特定的属性。因此，鸭子类型是由动态语言实现的。但是现在像 Haskell 这样的一些静态语言也支持它。但是，Java/C#还没有这个能力。

**示例:**现在，让我们看看如何在任何其他情况下使用对象，直到它不被支持。

```
# Python program to demonstrate
# duck typing

class Bird:
    def fly(self):
        print("fly with wings")

class Airplane:
    def fly(self):
        print("fly with fuel")

class Fish:
    def swim(self):
        print("fish swim in sea")

# Attributes having same name are
# considered as duck typing
for obj in Bird(), Airplane(), Fish():
    obj.fly()
```

**输出:**

```
fly with wings
fly with fuel

```

```
Traceback (most recent call last):
  File "/home/854855e5570b9ce4a9e984209b6a1c21.py", line 20, in 
    obj.fly()
AttributeError: 'Fish' object has no attribute 'fly'

```

在这个例子中，我们可以看到一个类支持一些方法，我们可以修改它或者给它们新的功能。鸭式强调对象真正能做什么，而不是对象是什么。