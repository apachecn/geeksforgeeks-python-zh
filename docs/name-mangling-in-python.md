# Python 中的名称漫画

> 原文:[https://www.geeksforgeeks.org/name-mangling-in-python/](https://www.geeksforgeeks.org/name-mangling-in-python/)

在名称管理过程中，任何带有两个前导下划线和一个尾随下划线的标识符在文本上都被替换为 **`_classname__identifier`** ，其中类名是当前类的名称。这意味着任何形式为 __geek 的标识符(至少两个前导下划线或最多一个尾随下划线)都被替换为 _ classname _ _ geek，其中 classname 是去掉前导下划线的当前类名。

**示例:**

```py
# Python program to demonstrate
# name mangling

class Student:
    def __init__(self, name):
        self.__name = name

    def displayName(self):
        print(self.__name)

s1 = Student("Santhosh")
s1.displayName()

# Raises an error
print(s1.__name)
```

**输出**

```py
Santhosh

```

```py
Traceback (most recent call last):
  File "/home/be691046ea08cd2db075d27186ea0493.py", line 14, in 
    print(s1.__name)
AttributeError: 'Student' object has no attribute '__name'

```

在上例中，类变量`__name`在类外不可访问。它只能在类内访问。对类变量的任何修改只能在类内部进行。

#### 名称管理流程

借助`dir()`方法，我们可以看到对类变量所做的名称 mangling 过程。名称篡改过程是由解释器完成的。通过传递类对象来使用`dir()`方法，它将返回属于该对象的所有有效属性。

```py
# Python program to demonstrate
# name mangling

class Student:
    def __init__(self, name):
        self.__name = name

s1 = Student("Santhosh")
print(dir(s1))
```

**输出**

> [' _ Student _ name '，' __class__ '，' __delattr__ '，' __dict__ '，' __dir__ '，' __doc__ '，' __eq__ '，' __format__ '，' __ge__ '，' __getattribute_ '，' __gt_ '，' __hash_ '，' __init_ '，' __le_ '，' __lt_ '，' __module__ '，' __ne__ '，'

上面的输出显示了`dir()`方法返回名称为 mangling process 的所有有效属性，这是对类变量 __name 完成的。姓名从 _ _ 姓名改为 _ _ 学生姓名。

#### 访问名称损坏的变量

名称管理过程有助于从类外部访问类变量。可以通过向类变量添加 _classname 来访问类变量。曼格林这个名字最接近于私人而不是确切的私人。

```py
# Python program to demonstrate
# name mangling

class Student:
    def __init__(self, name):
        self.__name = name

s1 = Student("Santhosh")
print(s1._Student__name)
```

**输出**

```py
Santhosh
```

通过向上面的类变量添加 _classname 来访问它。从名为 _ Student _ _ name 的类外部访问类变量。

#### 用方法重写命名 mangling

由于名称混淆，对类私有成员的有效用例的支持有限，基本上是为了避免名称与子类定义的名称的名称冲突。任何形式为 __geek 的标识符(至少两个前导下划线或最多一个尾随下划线)都被替换为 _ classname _ _ geek，其中 classname 是去掉前导下划线的当前类名。只要它出现在类的定义中，这种混淆就完成了。这有助于让子类在不中断类内方法调用的情况下重写方法。
让我们看看这个例子，并尝试找出这条下划线是如何工作的:

**示例:**

```py
# Python code to illustrate how mangling works 
# With method overriding

class Map: 
    def __init__(self): 
        self.__geek() 

    def geek(self): 
        print("In parent class") 

    # private copy of original geek() method 
    __geek = geek    

class MapSubclass(Map): 

    # provides new signature for geek() but 
    # does not break __init__() 
    def geek(self):         
        print("In Child class")

# Driver's code
obj = MapSubclass()
obj.geek()
```

**输出:**

```py
In parent class
In Child class

```