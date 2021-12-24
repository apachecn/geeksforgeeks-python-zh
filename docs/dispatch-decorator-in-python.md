# 用 Python 调度装饰器

> 原文:[https://www.geeksforgeeks.org/dispatch-decorator-in-python/](https://www.geeksforgeeks.org/dispatch-decorator-in-python/)

[](https://www.geeksforgeeks.org/decorators-in-python/)**是 Python 中非常强大和有用的工具，因为它允许程序员修改函数或类的行为。装饰器允许我们包装另一个函数，以便扩展包装函数的行为，而无需永久修改它。**

****示例:****

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

****输出:****

```py
Hello, this is before function execution
This is inside the function !!
This is after function execution 
```

## **调度装饰工**

**调度装饰器用于根据签名或类型列表在同一抽象方法的不同实现之间进行选择。**

****示例:****

```py
# Python program to demonstrate
# dispatch decorator

from multipledispatch import dispatch

@dispatch(int)
def func(x):
    return x * 2

@dispatch(float)
def func(x):
    return x / 2

# Driver code
print(func(2))
print(func(2.0))
```

****输出:****

```py
4
1.0
```

**在上例中，`@dispatch(int)`语句建议创建 Dispatcher‘func’，然后将‘int’类型分配为键，Dispatcher‘func’分配为值，并将其分配给命名空间(字典)中的 ith 索引。**

**现在你们一定都在想什么是名称空间？别担心，让我们看看命名空间。**

### **命名空间**

**命名空间只不过是调度装饰器使用的字典。调度装饰器用函数的名称创建一个调度器对象，并将该对象存储为键值对。该字典用于将上例中类似`func`的函数映射到类似`Disptacher('func')`的调度器对象。**

**默认情况下，使用的命名空间是 `multipledispatch.core.global_namespace`中的全局命名空间。为了增加安全性，可以使用字典建立自己的名称空间。**

****示例:****

```py
from multipledispatch import dispatch

nsp = {}

@dispatch(int, namespace = nsp)
def func(x):
    return x * 2

@dispatch(float, namespace = nsp)
def func(x):
    return x / 2

# Driver code
print(func(2))
print(func(2.0))
print(nsp)
```

****输出:****

```py
4
1.0
{'func': <dispatched func>}
```