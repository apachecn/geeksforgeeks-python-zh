# 在 Python 中创建嵌套数据类对象

> 原文:[https://www . geesforgeks . org/creating-nested-dataclass-objects-in-python/](https://www.geeksforgeeks.org/creating-nested-dataclass-objects-in-python/)

[数据类](https://www.geeksforgeeks.org/data-classes-in-python-an-introduction/)是一个内置的 Python 模块，包含装饰器和函数，用于自动向用户定义的类添加特殊方法，如 [__init__()](https://www.geeksforgeeks.org/__init__-in-python/) 和 __repr__()等。

数据类对象是构建在数据类模块中的对象。该函数用作装饰器，直接向用户定义的类添加特殊方法。这个装饰器检查类来查找字段(一个包含类型注释的类变量)。然后 dataclass 装饰器添加特殊的方法。

**语法:**

```
@dataclass
class user_defined_class:

```

在这里，我们将解决程序中嵌套数据类对象的问题。尽管数据类很容易使用，但它们仍然将程序的复杂性增加了一个小节，嵌套这样的对象可能看起来有点挑战性，但在这里我们将讨论每个场景以及如何处理它。

## 嵌套数据类对象

仔细查看以下代码:

```
@dataclass
class A:
    a: int
    b: str

@dataclass
class B:
    c: str
    d: A
```

从 A 类开始，它被一个数据类修饰。然后这个类被嵌套在类 B 中，作为 B 的一个字段，这个字段也被一个数据类对象修饰。到目前为止，这段代码只是展示了 dataclass 对象的嵌套，接下来我们将讨论如何使用这样的实现。

```
# importing module
from dataclasses import dataclass

@dataclass
class A:
    a: int
    b: str

@dataclass
class B:
    c: str
    d: A

# FIRST APPROACH
# creating object for class b with following values 
# c ='hello'
# a = 4
# b ='bye'
data ={'c':'hello', 'd':{'a':4, 'b':'bye'}}
b = B(**data)
print (b)

# SECOND APPROACH
data ={'c':'hello', 'd': A(**{'a':4, 'b':'bye'})}
c = B(**data)
print(c)
```

**输出:**

```
B(c='hello', d={'a': 4, 'b': 'bye'})
B(c='hello', d=A(a=4, b='bye'))
```

第一种方法的问题是输出没有给出嵌套对象或类 A 及其属性的概念，如果这是一个需求，那么我们就可以开始了。第二种方法很有效，但是如果您的 dataclass 对象中有多个嵌套对象，这似乎很乏味，不仅如此，随着嵌套对象数量的增加，程序的复杂性也会增加，调用它们的方法也会增加。因此，我们需要一种方法来实现第二种方法的输出，但又不会使调用和初始化过程变得复杂。

上述问题可以通过包装生成的 __init__()方法来解决，该方法将检查传递给 kwargs 的参数，检查是否有任何字段属于 dataclass 字段类型，以及它是否在原始 __init__()之前生成嵌套对象。

这意味着什么如下所示:

```
from dataclasses import dataclass, is_dataclass

# decorator to wrap original __init__
def nested_deco(*args, **kwargs):

    def wrapper(check_class):

        # passing class to investigate
        check_class = dataclass(check_class, **kwargs)
        o_init = check_class.__init__

        def __init__(self, *args, **kwargs):

            for name, value in kwargs.items():

                # getting field type
                ft = check_class.__annotations__.get(name, None)

                if is_dataclass(ft) and isinstance(value, dict):
                    obj = ft(**value)
                    kwargs[name]= obj
                o_init(self, *args, **kwargs)
        check_class.__init__=__init__

        return check_class

    return wrapper(args[0]) if args else wrapper

@dataclass
class A:
    a: int
    b: str

@nested_deco
class B:
    c: str
    d: A

data ={'c':'hello', 'd':{'a':4, 'b':'bye'}}
b = B(**data)
print (b)
```

**输出:**

```
B(c='hello', d=A(a=4, b='bye'))
```

请注意，除了 __init__()生成的问题之外，这也不允许 __init__=false 返回到代码中。