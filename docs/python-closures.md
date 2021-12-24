# Python 闭包

> 原文:[https://www.geeksforgeeks.org/python-closures/](https://www.geeksforgeeks.org/python-closures/)

在了解什么是闭包之前，我们必须先了解什么是嵌套函数和非局部变量。

### **Python 中的嵌套函数**

在另一个函数中定义的函数称为嵌套函数。嵌套函数能够访问封闭范围的变量。
在 Python 中，这些非局部变量只能在其作用域内访问，不能在其作用域外访问。下面的例子可以说明这一点:

## 计算机编程语言

```
# Python program to illustrate
# nested functions
def outerFunction(text):
    text = text

    def innerFunction():
        print(text)

    innerFunction()

if __name__ == '__main__':
    outerFunction('Hey!')
```

正如我们所看到的，innerFunction()可以很容易地在 outerFunction 主体内部访问，但不能在它的主体外部访问。因此，在这里，innerFunction()被视为嵌套函数，它使用**文本**作为非局部变量。

### **Python 闭包**

闭包是一个函数对象，即使内存中没有值，它也会记住封闭作用域中的值。

*   它是一个存储函数和环境的记录:将函数的每个自由变量(在本地使用但在封闭范围内定义的变量)与创建闭包时名称绑定到的值或引用相关联的映射。
*   闭包与普通函数不同，它允许函数通过闭包的值或引用副本来访问这些捕获的变量，即使函数在它们的作用域之外被调用。

## 蟒蛇 3

```
# Python program to illustrate
# closures
def outerFunction(text):
    text = text

    def innerFunction():
        print(text)

    # Note we are returning function
    # WITHOUT parenthesis
    return innerFunction 

if __name__ == '__main__':
    myFunction = outerFunction('Hey!')
    myFunction()
```

```
Output:
omkarpathak@omkarpathak-Inspiron-3542:
~/Documents/Python-Programs/$ python Closures.py 
Hey!
```

1.  从上面的代码可以看出，闭包有助于调用其范围之外的函数。
2.  功能**内部功能**的范围仅在外部功能内。但是通过使用闭包，我们可以很容易地扩展它的范围来调用它范围之外的函数。

## 蟒蛇 3

```
# Python program to illustrate
# closures
import logging
logging.basicConfig(filename='example.log',
                    level=logging.INFO)

def logger(func):
    def log_func(*args):
        logging.info(
            'Running "{}" with arguments {}'.format(func.__name__,
                                                    args))
        print(func(*args))

    # Necessary for closure to
    # work (returning WITHOUT parenthesis)
    return log_func            

def add(x, y):
    return x+y

def sub(x, y):
    return x-y

add_logger = logger(add)
sub_logger = logger(sub)

add_logger(3, 3)
add_logger(4, 5)

sub_logger(10, 5)
sub_logger(20, 10)
```

```
OUTPUT:
omkarpathak@omkarpathak-Inspiron-3542:
~/Documents/Python-Programs/$ python MoreOnClosures.py 
6
9
5
10
```

### **何时以及为何使用闭包:**

1.由于闭包被用作回调函数，它们提供了某种数据隐藏。这有助于我们减少全局变量的使用。

2.当我们的代码中很少有函数时，闭包被证明是一种有效的方法。但是如果我们需要很多功能，那就去上课(OOP)。

本文由 **Omkar Pathak** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。