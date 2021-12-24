# Python 中的函数包装器

> 原文:[https://www.geeksforgeeks.org/function-wrappers-in-python/](https://www.geeksforgeeks.org/function-wrappers-in-python/)

**函数周围的包装器**也被称为 **[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)** ，这是 Python 中非常强大和有用的工具，因为它允许程序员修改函数或类的行为。装饰器允许我们包装另一个函数，以便扩展包装函数的行为，而无需永久修改它。在 Decorators 中，函数被当作另一个函数的参数，然后在包装函数中调用。

**语法:**

```py
@wrapper
def function(n):
    statements(s)
```

这也类似于

```py
def function(n):
    statement(s)

function = wrapper(function)
```

让我们看看下面的例子，以便更好地理解。
**例 1:**

```py
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

```py
Hello, this is before function execution
This is inside the function !!
This is after function execution
```

**示例 2:** 让我们定义一个装饰器，计算函数执行所花费的时间。

```py
import time

def timeis(func):
    '''Decorator that reports the execution time.'''

    def wrap(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()

        print(func.__name__, end-start)
        return result
    return wrap

@timeis
def countdown(n):
    '''Counts down'''
    while n > 0:
        n -= 1

countdown(5)
countdown(1000)
```

**输出:**

```py
countdown 1.6689300537109375e-06
countdown 5.507469177246094e-05
```

需要强调的是，装饰者通常不会改变被包装函数的调用签名或返回值。使用 ***args** 和 ****kwargs** 是为了确保可以接受任何输入参数。装饰器的返回值几乎总是调用 **func(*args，**kwargs)** 的结果，其中 func 是原始的展开函数。

更多详情请参考 Python 中的[装饰器](https://www.geeksforgeeks.org/decorators-in-python/)。