# Python 中的高阶函数

> 原文:[https://www . geesforgeks . org/python 中的高阶函数/](https://www.geeksforgeeks.org/higher-order-functions-in-python/)

如果一个函数包含其他函数作为参数或返回一个函数作为输出，即与另一个函数一起运行的函数称为高阶函数，则该函数称为**高阶函数**。值得知道的是，这个高阶函数也适用于以函数为参数或以函数为结果的函数和方法。Python 也支持高阶函数的概念。

**高阶函数的属性:**

*   A function is an instance of an object type.
*   Functions can be stored in variables.
*   You can pass a function as a parameter to another function.
*   You can return a function from a function.
*   You can store them in hash tables, lists and other data structures ...

#### 作为对象的功能

在 Python 中，一个函数可以被分配给一个变量。此赋值不调用函数，而是创建对该函数的引用。考虑下面的例子，以便更好地理解。

**例:**

```
# Python program to illustrate functions 
# can be treated as objects 
def shout(text): 
    return text.upper() 

print(shout('Hello')) 

# Assigning function to a variable
yell = shout 

print(yell('Hello'))
```

**输出:**

```
HELLO
HELLO

```

在上面的例子中，一个被 shout 引用的函数对象创建了指向它的第二个名字，shout。

#### 将函数作为参数传递给其他函数

函数就像 Python 中的对象，因此，它们可以作为参数传递给其他函数。考虑下面的例子，我们已经创建了一个函数 greet，它以一个函数作为参数。

**例:**

```
# Python program to illustrate functions 
# can be passed as arguments to other functions 
def shout(text): 
    return text.upper() 

def whisper(text): 
    return text.lower() 

def greet(func): 
    # storing the function in a variable 
    greeting = func("Hi, I am created by a function \
    passed as an argument.") 
    print(greeting)  

greet(shout) 
greet(whisper)
```

**输出:**

```
HI, I AM CREATED BY A FUNCTION PASSED AS AN ARGUMENT.
hi, i am created by a function passed as an argument.

```

#### 返回函数

由于函数是对象，我们也可以从另一个函数返回一个函数。在下面的例子中，create_adder 函数返回加法器函数。

**示例:**

```
# Python program to illustrate functions 
# Functions can return another function 

def create_adder(x): 
    def adder(y): 
        return x + y 

    return adder 

add_15 = create_adder(15) 

print(add_15(10))
```

**输出:**

```
25

```

## 装饰者

装饰器是 Python 中最常用的高阶函数。它允许程序员修改函数或类的行为。装饰器允许我们包装另一个函数，以便扩展包装函数的行为，而无需永久修改它。在 Decorators 中，函数被当作另一个函数的参数，然后在包装函数中调用。

**语法:**

```
@gfg_decorator
def hello_decorator(): 
    .
    .
    .

```

以上代码相当于–

```

def hello_decorator(): 
    .
    .
    .

hello_decorator = gfg_decorator(hello_decorator)

```

在上面的代码中，`gfg_decorator`是一个可调用函数，将一些代码添加在一些另一个可调用函数的上面，`hello_decorator`函数又返回了包装函数。

**例:**

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

**注意:**更多信息请参考 Python 中的[装饰者](https://www.geeksforgeeks.org/decorators-in-python/)。