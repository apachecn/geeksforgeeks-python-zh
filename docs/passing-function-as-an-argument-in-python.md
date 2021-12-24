# 在 Python 中将函数作为参数传递

> 原文:[https://www . geesforgeks . org/passing-function-as-argument-in-python/](https://www.geeksforgeeks.org/passing-function-as-an-argument-in-python/)

一个函数可以有多个参数，这些参数可以是对象、变量(数据类型相同或不同)和函数。Python 函数是[第一类](https://www.geeksforgeeks.org/first-class-functions-python/)对象。在下面的例子中，一个函数被分配给一个变量。这个赋值不调用函数。它接受 shout 引用的函数对象，并创建指向它的第二个名称，shout。

```
# Python program to illustrate functions 
# can be treated as objects 
def shout(text): 
    return text.upper() 

print(shout('Hello')) 

yell = shout 

print(yell('Hello')) 
```

**输出:**

```
HELLO
HELLO

```

## 高阶函数

因为函数是对象，所以我们可以将它们作为参数传递给其他函数。可以接受其他函数作为自变量的函数也称为**高阶函数**。在下面的示例中，创建了一个函数 greet，它将函数作为参数。

```
# Python program to illustrate functions 
# can be passed as arguments to other functions 
def shout(text): 
    return text.upper() 

def whisper(text): 
    return text.lower() 

def greet(func): 
    # storing the function in a variable 
    greeting = func("Hi, I am created by a function passed as an argument.") 
    print(greeting)

greet(shout) 
greet(whisper) 
```

**输出**

```
HI, I AM CREATED BY A FUNCTION PASSED AS AN ARGUMENT.
hi, i am created by a function passed as an argument.

```

## 包装函数

包装函数或装饰器允许我们包装另一个函数，以便扩展包装函数的行为，而无需永久修改它。在 Decorators 中，函数被当作另一个函数的参数，然后在包装函数中调用。想了解更多关于装饰器的信息[点击这里](https://www.geeksforgeeks.org/decorators-in-python/)。

下面是一个简单的装饰器的例子。

```
# defining a decorator 
def hello_decorator(func): 

    # inner1 is a Wrapper function in  
    # which the argument is called 

    # inner function can access the outer local 
    # functions like in this case "func" 
    def inner1(): 
        print("Hello, this is before function execution") 

        # calling the actual function now 
        # inside the wrapper function. 
        func() 

        print("This is after function execution") 

    return inner1 

# defining a function, to be called inside wrapper 
def function_to_be_used(): 
    print("This is inside the function !!") 

# passing 'function_to_be_used' inside the 
# decorator to control its behavior 
function_to_be_used = hello_decorator(function_to_be_used) 

# calling the function 
function_to_be_used() 
```

**输出:**

```
Hello, this is before function execution
This is inside the function !!
This is after function execution

```

## Lambda 包装函数

在 Python 中，匿名函数意味着函数没有名称。我们已经知道`def` 关键字用于定义正常函数，`lambda` 关键字用于创建匿名函数。此函数可以有任意数量的参数，但只能有一个表达式，该表达式将被计算并返回。[λ函数](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)也可以有另一个函数作为自变量。下面的例子展示了一个基本的[λ函数](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)，其中另一个λ函数作为参数被传递。

```
# Defining lambda function
square = lambda x:x * x

# Defining lambda function
# and passing function as an argument
cube = lambda func:func**3

print("square of 2 is :"+str(square(2)))
print("\nThe cube of "+str(square(2))+" is " +str(cube(square(2))))
```

**输出:**

```
square of 2 is :4

The cube of 4 is 64

```