# Python 中的析构函数

> 原文:[https://www.geeksforgeeks.org/destructors-in-python/](https://www.geeksforgeeks.org/destructors-in-python/)

[Python 中的构造函数](https://www.geeksforgeeks.org/constructors-in-python/)

当一个对象被销毁时，就调用析构函数。在 Python 中，析构函数不像 C++中那么需要，因为 Python 有一个垃圾收集器，可以自动处理内存管理。
**_ _[del](https://www.geeksforgeeks.org/delattr-del-python/)_ _()**方法在 Python 中被称为析构函数方法。当对象的所有引用都被删除时，即当对象被垃圾收集时，调用该函数。
**析构函数声明语法:**

```
def __del__(self):
  # body of destructor
```

 **注意:**当对象失去引用或程序结束时，对对象的引用也会被删除。

**例 1 :** 下面是析构函数的简单例子。通过使用 del 关键字，我们删除了对象“obj”的所有引用，因此析构函数被自动调用。

```
# Python program to illustrate destructor
class Employee:

    # Initializing
    def __init__(self):
        print('Employee created.')

    # Deleting (Calling destructor)
    def __del__(self):
        print('Destructor called, Employee deleted.')

obj = Employee()
del obj
```

**Output:**

```
Employee created.
Destructor called, Employee deleted.

```

**注意:**在程序结束后或者当所有对对象的引用都被删除时，即当引用计数变为零时，而不是当对象超出范围时，析构函数被调用**。**

**例 2 :** 本例给出了上述注释的解释。这里，请注意，析构函数是在“程序结束……”打印后调用的。

```
# Python program to illustrate destructor

class Employee:

    # Initializing 
    def __init__(self):
        print('Employee created')

    # Calling destructor
    def __del__(self):
        print("Destructor called")

def Create_obj():
    print('Making Object...')
    obj = Employee()
    print('function end...')
    return obj

print('Calling Create_obj() function...')
obj = Create_obj()
print('Program End...')
```

**Output:**

```
Calling Create_obj() function...
Making Object...
Employee created
function end...
Program End...
Destructor called

```

**示例 3 :** 现在，考虑以下示例:

```
# Python program to illustrate destructor

class A:
    def __init__(self, bb):
        self.b = bb

class B:
    def __init__(self):
        self.a = A(self)
    def __del__(self):
        print("die")

def fun():
    b = B()

fun()
```

**Output:**

```
die

```

在本例中，当函数 fun()被调用时，它会创建一个 B 类的实例，该实例将自身传递给 A 类，然后 A 类设置对 B 类的引用，并产生一个**循环引用**。

一般来说，Python 中用于检测这些类型的循环引用的垃圾收集器会将其移除，但是在本例中，自定义析构函数的使用将该项标记为“无法收集”。
简单来说，它不知道破坏物体的顺序，所以就离开了它们。因此，**如果您的实例涉及循环引用，那么只要应用程序运行，它们就会一直存在于内存中。**