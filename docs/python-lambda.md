# Pythonλ

> 原文:[https://www.geeksforgeeks.org/python-lambda/](https://www.geeksforgeeks.org/python-lambda/)

在 Python 中，匿名函数意味着函数没有名称。正如我们已经知道的，def 关键字用于定义普通函数，lambda 关键字用于创建匿名函数。它具有以下语法:

**语法:**

```py
lambda arguments : expression 
```

*   此函数可以有任意数量的参数，但只能有一个表达式，该表达式将被计算并返回。
*   只要需要函数对象，就可以自由使用 lambda 函数。
*   您需要记住，lambda 函数在语法上仅限于单个表达式。
*   除了函数中的其他类型的表达式之外，它在特定的编程领域还有各种用途。

**示例#1:**

## 蟒蛇 3

```py
# Python program to demonstrate
# lambda functions

string ='GeeksforGeeks'

# lambda returns a function object
print(lambda string : string)
```

**输出:**

```py
<function <lambda> at 0x7f268eb16f28>
```

在上面的例子中，lambda 不是由 print 函数调用的，而是简单地返回函数对象及其存储位置。
所以，要让 print 首先打印字符串，我们需要调用 lambda，这样字符串就可以通过打印。
**例 2:**

## 蟒蛇 3

```py
# Python program to demonstrate
# lambda functions

x ="GeeksforGeeks"

# lambda gets pass to print 
(lambda x : print(x))(x)
```

**输出:**

```py
GeeksforGeeks
```

**示例# 3:**lambda 和正常函数调用的区别

## 蟒蛇 3

```py
# Python program to illustrate cube of a number  
# showing difference between def() and lambda().

def cube(y): 
    return y*y*y; 

g = lambda x: x*x*x 
print(g(7)) 

print(cube(5))
```

**输出:**

```py
343
125
```

**示例#4:** 在函数内部使用 lambda 函数会更有帮助。

## 蟒蛇 3

```py
# Python program to demonstrate
# lmabda functions

def power(n):
    return lambda a : a ** n

# base = lambda a : a**2 get 
# returned to base
base = power(2)

print("Now power is set to 2")

# when calling base it gets 
# executed with already set with 2
print("8 powerof 2 = ", base(8))

# base = lambda a : a**5 get 
# returned to base
base = power(5)
print("Now power is set to 5")

# when calling base it gets executed
# with already set with newly 2
print("8 powerof 5 = ", base(8))
```

**输出:**

```py
Now power is set to 2
8 powerof 2 =  64
Now power is set to 5
8 powerof 5 =  32768
```

我们还可以通过使用 map()方法用 lambda 替换列表理解，这不仅是一个快速但高效的方法，让我们看看如何在过滤器()中使用 Lambda。
**示例#5:** 滤镜()和贴图(

## 蟒蛇 3

```py
# Python program to demonstrate
# lambda functions inside map()
# and filter()

a = [100, 2, 8, 60, 5, 4, 3, 31, 10, 11]

# in filter either we use assignment or 
# conditional operator, the pass actual 
# parameter will get return
filtered = filter (lambda x: x % 2 == 0, a) 
print(list(filtered))

# in map either we use assignment or
# conditional operator, the result of 
# the value will get returned
maped = map (lambda x: x % 2 == 0, a) 
print(list(maped))
```

**输出:**

```py
[100, 2, 8, 60, 4, 10]
[True, True, True, True, False, True, False, False, True, False]
```