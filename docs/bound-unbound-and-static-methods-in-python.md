# Python 中的绑定、未绑定和静态方法

> 原文:[https://www . geesforgeks . org/bind-unbound-static-in-methods-python/](https://www.geeksforgeeks.org/bound-unbound-and-static-methods-in-python/)

Python 中的方法类似于函数，只是它附加到一个对象上。这些方法是在对象上调用的，它可能会对该对象进行更改。这些方法可以是绑定、未绑定或静态方法。静态方法是未绑定方法的类型之一。这些类型将在下面详细解释。

## 绑定方法

如果一个函数是类的一个属性，并且它是通过实例访问的，那么它们被称为绑定方法。绑定方法是以“`[self](https://www.geeksforgeeks.org/self-in-python-class/)`”作为其第一个参数的方法。因为它们依赖于类的实例，所以也称为实例方法。

#### 需要这些绑定方法

类中的方法至少需要一个参数。要使它们成为零参数方法，必须使用“`[decorators](https://www.geeksforgeeks.org/decorators-in-python/)`”。类的不同实例有不同的关联值。

例如，如果有一个“水果”类，像苹果、橘子、芒果这样的例子是可能的。每个实例可能有不同的大小、颜色、味道和营养成分。因此，要更改特定实例的任何值，该方法必须有“self”作为参数，允许它只更改其属性。

**例:**

```
class sample(object):

    # Static variable for object number
    objectNo = 0

    def __init__(self, name1):

        # variable to hold name
        self.name = name1

        # Increment static variable for each object
        sample.objectNo = sample.objectNo + 1

        # each object's unique number that can be
        # considered as ID
        self.objNumber = sample.objectNo

    def myFunc(self):
        print("My name is ", self.name, 
              "from object ", self.objNumber)

    def alterIt(self, newName):
        self.name = newName

    def myFunc2():
        print("I am not a bound method !!!")

# creating first instance of class sample        
samp1 = sample("A")
samp1.myFunc()

# unhide the line below to see the error
# samp1.myFunc2() #----------> error line

# creating second instance of class sample    
samp2 = sample("B")
samp2.myFunc()
samp2.alterIt("C")
samp2.myFunc()
samp1.myFunc()
```

**输出:**

```
My name is  A from object  1
My name is  B from object  2
My name is  C from object  2
My name is  A from object  1

```

在上面的示例中，创建了两个实例，即 samp1 和 samp2。请注意，当函数 `alterIt()`应用于第二个实例时，只有该特定实例的值会改变。线路 **samp1.myFunc()** 将扩展为**samp 1 . my func(samp 1)**。对于此方法，不需要传递显式参数。实例 samp1 将作为参数传递给 myFunc()。第**行采样 1.myFunc2()** 会产生错误:

```
Traceback (most recent call last):
  File "/home/4f130d34a1a72402e0d26bab554c2cf6.py", line 26, in 
    samp1.myFunc2() #----------> error line
TypeError: myFunc2() takes 0 positional arguments but 1 was given

```

表示此法为**未绑定**。它不接受任何实例作为参数。这些函数是未绑定的函数。

## 未绑定方法和静态方法

没有类实例作为第一个参数的方法称为未绑定方法。从 Python 3.0 开始，未绑定的方法已经从语言中移除。它们不受类的任何特定对象的限制。要使方法 **myFunc2()** 在上面的类中工作，它应该被制成一个**静态方法**

静态方法类似于类方法，但完全绑定到类，而不是特定的对象。使用类名访问它们。

#### 需要使方法静态化

不是所有的方法都需要改变类的实例。它们可能有任何共同的目的。方法也可以是效用函数。

例如，当我们需要使用某些数学函数时，我们使用内置类`Math`。这个类中的方法是静态的，因为它们与特定的对象无关。他们做共同的行动。因此，每次写为:

```
math=Math()
math.ceil(5.23)
```

都不是最佳方式

因此可以简单地使用类名`**Math.ceil(5.23)**`来访问它们。

一个方法可以通过两种方式变成静态的:

1.  使用 staticmethod()
2.  使用装饰者

**使用 staticmethod():** 函数将待转换的函数作为参数，并返回该函数的静态版本。静态函数对该类一无所知，它只使用传递给它的参数。

**例:**

```
class sample():

      def myFunc2(x):

             print("I am", x, "from the static method")

sample.myFunc2 = staticmethod(sample.myFunc2)
sample.myFunc2("A")
```

**输出:**

```
I am A from the static method

```

**使用装饰器:**这些是 Python 的特性，用于在编译时使用程序的另一部分修改程序的一部分。可以用来使方法静态化的装饰器是

```
@staticmethod
```

这通知内置默认元类不要为此方法创建任何绑定方法。一旦在函数之前添加了这一行，就可以使用类名调用函数。考虑我们遇到错误的绑定方法的例子。为了克服这一点，可以写成:

```
class sample(object):

    # Static variable for object number
    objectNo = 0

    def __init__(self, name1):
        # variable to hold name
        self.name = name1

        # Increment static variable for each object
        sample.objectNo = sample.objectNo + 1

        # each object's unique number that can be
        # considered as ID
        self.objNumber = sample.objectNo

    def myFunc(self):
        print("My name is ", self.name, 
              "from object ", self.objNumber)

    def alterIt(self, newName):
        self.name = newName

    # using decorator to make the method static
    @staticmethod
    def myFunc2():
        print("I am not a bound method !!!")

# creating first instance of class sample        
samp1 = sample("A")
samp1.myFunc()

sample.myFunc2() #----------> error line

# creating second instance of class sample    
samp2 = sample("B")
samp2.myFunc()
samp2.alterIt("C")
samp2.myFunc()
samp1.myFunc()
```

**输出:**

```
My name is  A from object  1
I am not a bound method !!!
My name is  B from object  2
My name is  C from object  2
My name is  A from object  1

```

这里，行 **sample.myFunc2()** 运行没有任何错误，其中的 print()工作完美，给出了输出**我不是绑定方法！！！**