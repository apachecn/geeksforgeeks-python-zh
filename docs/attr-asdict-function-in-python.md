# Python 中的 attr.asdict()函数

> 原文:[https://www . geesforgeks . org/attr-asdict-python 中的函数/](https://www.geeksforgeeks.org/attr-asdict-function-in-python/)

Python 有一个名为 **attrs** 的库，这使得以面向对象模式编写的代码更加容易和简洁。在有数据的类中，最好把它转换成字典。我们可以使用 Python 中的 attr.asdict()函数将 I 的**attr**属性值作为 dict 返回。

> **语法:** attr.asdict (inst，recurse: bool=True，filter: __class__=None，dict_factory:，retain _ collection _ type:bool = False)
> 
> **参数:**
> **inst**:attrs 修饰类的实例
> **递归**:(布尔型)递归到同样是 attrs 修饰类的类中
> **dict_factory** :一个从
> **过滤器**生成字典的可调用函数:一个确定属性是被包含(真)还是被丢弃(假)
> **retain _ collection _ type**:只有递归时才有意义

**示例 1:** 我们举一个非常简单的类坐标的例子，它接受坐标作为属性。

## 蟒蛇 3

```py
# import library
import attr

# initialising class Coordinates, no need to
# initialize __init__ method
@attr.s
class Coordinates(object):

    # attributes
    x = attr.ib()
    y = attr.ib()

c1 = Coordinates(1, 2)

# converting data into dict using attr.asdict() 
# function
print(attr.asdict(Coordinates(x=1, y=2)))
```

**输出:**

```py
{'x': 1, 'y': 2}
```

这里，传递的数据被转换成字典形式。

**示例 2:** 这里是类 User Info 的另一个示例，它将接受用户的姓名和电子邮件 id 作为属性，但不会以 dict 形式的数据包含用户的电子邮件 id。

## 蟒蛇 3

```py
import attr

@attr.s
class UserInfo(object):
    users = attr.ib()

@attr.s
class User(object):
    email = attr.ib()
    name = attr.ib()

# including only name and not email
attr.asdict(UserInfo([User("lee@har.invalid", "Lee"),
                      User("rachel@har.invalid", "Rachel")]),
            filter=lambda attr, value: attr.name != "email")
```

**输出:**

```py
{'users': [{'name': 'Lee'}, {'name': 'Rachel'}]}
```

在这里，我们将得到一个嵌套的字典，其中不包括用户的电子邮件。

**示例 3:** 我们可以尝试使用 attr.asdict()函数的参数*过滤器*来包含或排除属性的不同方法。

## 蟒蛇 3

```py
import attr

@attr.s
class UserInfo(object):
    name = attr.ib()
    password = attr.ib()
    age = attr.ib()

# excluding attributes
print(attr.asdict(UserInfo("Marco", "abc@123", 22),
                  filter=attr.filters.exclude(
                      attr.fields(UserInfo).password, int)))

@attr.s
class Coordinates(object):
    x = attr.ib()
    y = attr.ib()
    z = attr.ib()

# inclusing attributes
print(attr.asdict(Coordinates(20, "5", 3),
                  filter=attr.filters.include(int)))
```

**输出:**

```py
{'name': 'Marco'}
{'x': 20, 'z': 3}
```

这里，在类 *UserInfo* 中，我们传递了三个参数名称、密码和年龄，其中年龄是一个整数值，其余的值是字符串。在过滤器参数中，我们排除了属性–密码和整数值(此处为年龄)，因此密码和年龄将从字典中排除。

在类*坐标*中，我们传递了三个参数——x、y 和 z 坐标。这里 y 坐标作为字符串传递。在过滤器参数中，我们包含了整数值。因此，x 和 z 坐标包含在最终字典中。如果 y 坐标是作为整数传递的，那么它也应该包含在内。