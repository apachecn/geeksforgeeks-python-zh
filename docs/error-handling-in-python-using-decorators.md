# 使用装饰器处理 Python 中的错误

> 原文:[https://www . geesforgeks . org/python 中的错误处理-使用-装饰器/](https://www.geeksforgeeks.org/error-handling-in-python-using-decorators/)

[Python 中的 decorator](https://www.geeksforgeeks.org/decorators-in-python/)是 Python 支持的最有用的概念之一。它以函数作为参数，也有一个嵌套函数。它们扩展了嵌套函数的功能。

**示例:**

## 蟒蛇 3

```py
# defining decorator function
def decorator_example(func):
    print("Decorator called")
    # defining inner decorator function
    def inner_function():
            print("inner function")
            func()
    return inner_function

# defining outer decorator function
@decorator_example
def out_function():
    print("outer function")
out_function()
```

**输出:**

```py
Decorator called
inner function
outer function
```

### 使用装饰器处理错误

以下示例显示了不使用任何装饰器的一般错误处理代码是什么样子的:

## 蟒蛇 3

```py
def mean(a,b):
    try:
        print((a+b)/2)
    except TypeError:
        print("wrong data types. enter numeric")

def square(sq):
    try:
        print(sq*sq)
    except TypeError:
        print("wrong data types. enter numeric")

def divide(l,b):
    try:
        print(b/l)
    except TypeError:
                print("wrong data types. enter numeric")
mean(4,5)
square(21)
divide(8,4)
divide("two","one")
```

**输出:**

```py
4.5
441
0.5
wrong data types. enter numeric
```

即使上面的代码在逻辑上没有问题，但是它缺乏清晰度。为了使代码更加干净和高效，装饰器被用于错误处理。下面的例子描述了如何通过使用装饰器使上面的代码更加形象和易于理解:

## 蟒蛇 3

```py
def Error_Handler(func):
    def Inner_Function(*args, **kwargs):
        try:
            func(*args, **kwargs)
        except TypeError:
            print(f"{func.__name__} wrong data types. enter numeric")
    return Inner_Function
@Error_Handler
def Mean(a,b):
        print((a+b)/2)

@Error_Handler
def Square(sq):
        print(sq*sq)

@Error_Handler
def Divide(l,b):
        print(b/l)

Mean(4,5)
Square(14)
Divide(8,4)
Square("three")
Divide("two","one")
Mean("six","five")
```

**输出:**

> 4.5 
> 
> 196 
> 
> 0.5 
> 
> 纠正错误的数据类型。输入数字
> 
> 划分错误的数据类型。输入数字
> 
> 意味着错误的数据类型。输入数字