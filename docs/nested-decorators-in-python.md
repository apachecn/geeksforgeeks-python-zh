# Python 中的嵌套装饰器

> 原文:[https://www.geeksforgeeks.org/nested-decorators-in-python/](https://www.geeksforgeeks.org/nested-decorators-in-python/)

Python 中的一切都是一个对象。偶数函数是 Python 中的一种对象类型。[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)是返回包装函数的一种特殊类型的函数。它们在 Python 中被认为非常强大，用于临时修改函数的行为，而不会改变其实际值。

嵌套意味着放置或储存在另一个里面。因此，嵌套装饰器意味着在一个函数中应用多个装饰器。Python 允许我们为一个函数实现多个装饰器。它使装饰者对可重用的构建块有用，因为它将几种效果累积在一起。

## **几个装修师是怎么应用的？**

一个函数可以修饰多次。我们需要首先定义我们想要包装输出字符串的装饰器，然后使用“@”将它们应用于函数。人们只需要把装饰者放在想要的功能之上。

**语法:**

```
*@function1*
*@function2*
*def function(name):*
 *print(f"{name}")*
```

嵌套装饰遵循自下而上的方法，即相反的顺序。它可以与我们从底部(地面)开始建造，然后开始建造楼层的建筑相关。

**例:**

## 蟒 3

```
# Python program to demonstrate
# nested decorators

def italic(func):

    def wrapper():
        return '<i>' + func() + '</i>'

    return wrapper

def strong(func):

    def wrapper():
        return '<strong>' + func() + '</strong>'

    return wrapper

@italic
@strong
def introduction():
    return 'This is a basic program'

print(introduction())
```

**输出:**

```
<i><strong>This is a basic program</strong></i>
```

**说明:**

1.  First, we define two decorators, which are used to wrap the output string of the decorator function in the' strong' and' italics' tags of *HTML.*
2.  Then we apply these two decorators to our "Introduction" function by using an "@" and a function name. For example, in this program, we used @italic and @strong.
3.  The level it follows is from bottom to top. Therefore, according to it, the string is first wrapped with "strong" and then wrapped with "italic".