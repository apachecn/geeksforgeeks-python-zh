# 如何创建同时在 Python2 和 Python3 上运行的元类实例？

> 原文:[https://www . geeksforgeeks . org/如何创建一个元类实例，该实例在两个 python2 和 python3 上运行/](https://www.geeksforgeeks.org/how-to-create-an-instance-of-a-metaclass-that-run-on-both-python2-and-python3/)

[元类](https://www.geeksforgeeks.org/python-metaclasses/)是生成其他类的类。它是一个高效的类验证工具，可以防止子类继承某些类函数，以及类的动态生成。这里我们将讨论如何创建一个运行在 Python 2 和 Python 3 上的元类实例。在深入研究之前，让我们先看看每个 Python 版本的代码设计。

### 蟒蛇 3

在 Python 3 中，通过向元类关键字参数提供元类，在声明类时创建元类的实例。让我们看看 Python 3 中实现这一点的首选方式。

## 蟒蛇 3

```
class MetaCls(type):
  def __new__(cls, name, bases, attrs):
    return super(MetaCls, cls).__new__(cls, name, bases, attrs)

class C(object, metaclass=MetaCls):
  pass

print('Type of class C:',type(C))
```

**Output**

```
Type of class C: <class '__main__.MetaCls'>

```