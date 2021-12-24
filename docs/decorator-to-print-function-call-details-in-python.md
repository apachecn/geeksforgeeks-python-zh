# 装饰器打印 Python 中的函数调用细节

> 原文:[https://www . geesforgeks . org/decorator-to-print-function-call-details-in-python/](https://www.geeksforgeeks.org/decorator-to-print-function-call-details-in-python/)

[Python 中的装饰器](https://www.geeksforgeeks.org/decorators-in-python/)是一种设计模式，允许用户向现有对象添加新功能，而无需修改其结构。装饰器通常在定义用户想要装饰的功能之前被调用。

**例:**

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