# 类工厂:Python 中强大的模式

> 原文:[https://www . geesforgeks . org/class-factors-一种强大的 python 模式/](https://www.geeksforgeeks.org/class-factories-a-powerful-pattern-in-python/)

类工厂是一个创建和返回类的函数。它是 Python 中强大的模式之一。在本节中，我们将介绍如何设计类工厂及其用例。

## 设计班级工厂

如上所述，类工厂是创建和返回类的函数。它可以在编码时(使用 class 关键字)和运行时(使用 type)创建一个类。让我们从如何设计一个类工厂并在编码时创建一个类开始，然后我们研究在运行时创建一个类的场景。

### 类工厂和类关键字

使用 class 关键字设计类工厂只不过是创建一个保存类的函数。让我们看看下面的代码:

## 蟒蛇 3

```
def apple_function():
    """Return an Apple class, built using the 
    class keyword"""
    class Apple(object):
        def __init__(self, color):
            self.color = color

        def getColor(self):
            return self.color
    return Apple

# invoking class factory function
Apple = apple_function()
appleObj = Apple('red')
print(appleObj.getColor())
```

**Output**

```
red

```

### 类别工厂和类型

使用类型，我们可以动态地创建类。但是这样做会将函数和类一起留在命名空间中。让我们看看代码，以便更好地理解它。

T3】蟒 3T5

```
def init(self, color):
    self.color = color

def getColor(self):
    return self.color

Apple = type('Apple', (object,), {
    '__init__': init,
    'getColor': getColor,
})

appleRed = Apple(color='red')
print(appleRed.getColor())
```

T6T8**输出**T1

上面的代码展示了如何动态创建类。但问题是像 init 和 getColor 这样的函数会使名称空间变得混乱，而且我们也不能重用这些功能。然而，通过使用类工厂，您可以最小化混乱，并在需要时重用该功能。让我们看看下面的代码。

T3】蟒 3T5

```
def create_apple_class():
    def init(self, color):
        self.color = color

    def getColor(self):
        return self.color

    return type('Apple', (object,), {
        '__init__': init,
        'getColor': getColor,
    })

Apple = create_apple_class()
appleObj = Apple('red')
print(appleObj.getColor())
```

T6T8**输出**T1

需要注意的是，多次调用 create_apple_class 将返回不同的类。

## 你什么时候应该写类工厂

让我们来看看类工厂的一些用例。当您不知道在编码时要分配什么属性时，类工厂非常有用

### 运行时属性

当类的属性根据需求不同时，类工厂是必要的。让我们考虑登录过程的情况。在这里，我们将考虑两种情况，传统登录或使用 OpenId 服务。如果我们查看传统登录，参数是用户名和密码，此外，它可能具有双因素身份验证。而且，对于 OpenId 服务，参数是服务名称和电子邮件地址。这两个登录场景指出了一个事实，即类的属性根据登录服务而不同。让我们看看下面的示例代码:

## 蟒蛇 3

```
def credentials_cls(need_proxy=False, tfa=False):
    # need proxy for openId services
    if need_proxy:
        print("Open Id Service")
        keys = ['service_name', 'email_address']
    else:
        print("Traditional Login")
        keys = ['username', 'password']

        # two factor authentication for traditional login
        if tfa:
            keys.append('auth_token')

    class CredentialCheck(object):
        required_keys = set(keys)

        def __init__(self, **kwargs):
            # checking whether key matches based on login service
            if self.required_keys != set(kwargs.keys()):
                raise ValueError('Mismatch')

            # storing the keys and values to the credential object
            for k, v in kwargs.items():
                setattr(self, k, v)

    return CredentialCheck

CredCheck = credentials_cls(False, False)
crdTraditional = CredCheck(username='uname', password='******')

OpenIDCheck = credentials_cls(True, False)
crdOpenID = OpenIDCheck(service_name='sname', email_address='email@gmail.com')
```

**Output**

```
Traditional Login
Open Id Service

```

### 修改类属性

使用类属性的另一个优点是，它可以处理类属性，并且可以将它们与类实例区分开来。让我们考虑一个类定义一个类方法的场景。类方法是需要类本身来执行的方法，而不是类的实例。您可以通过使用@classmethod 装饰器装饰方法来设计类方法。让我们看看下面的代码。

T3】蟒 3T5

```
class Apple(object):
    color = 'red'

    @classmethod
    def classapple(cls):
        return cls.color

appleRed = Apple()
appleYellow = Apple()
appleGreen = Apple()

print("Apple Red: ", appleRed.classapple())

appleYellow.color = 'Yellow'
print("Apple Yellow: ", appleYellow.classapple())

appleGreen.color = 'Green'
print("Apple Green: ", appleGreen.classapple())
```

T6T8**输出**T1

在上面的代码中，我们设计了一个名为 *Apple* 的类，它以颜色作为属性。除此之外，我们还使用装饰器 *@classmethod* 声明了一个名为 *classapple* 的类方法。*类苹果*方法的功能是返回苹果的颜色。但是，您可以注意到，即使将苹果的颜色设置为黄色和绿色，对象也会返回默认颜色红色。使用类工厂可以克服这个限制。

让我们看看下面的代码，它定义了一个名为 create_Apple_subclass 的类工厂。在这里，我们将创建一个苹果的子类，subApple，来设置颜色。最后，类工厂返回子类。

## 蟒 3

```
class Apple(object):
    color = 'red'

    @classmethod
    def classapple(cls):
        return cls.color

def create_Apple_subclass(new_color):
    class SubApple(Apple):
        color = new_color
    return SubApple

sappleYellow = create_Apple_subclass('Yellow')
print("Apple Color: ", sappleYellow.classapple())

sappleGreen = create_Apple_subclass('Green')
print("Apple Color: ", sappleGreen.classapple())
```

**输出**

```
Apple Color:  Yellow
Apple Color:  Green

```

## 摘要

类工厂是强大的设计模式，确保动态的类创建过程是可读的、有组织的和可重用的。此外，类工厂还允许基于发送给函数的参数进行属性切换。