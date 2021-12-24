# Python |如何获取函数名？

> 原文:[https://www . geesforgeks . org/python-如何获取函数名/](https://www.geeksforgeeks.org/python-how-to-get-function-name/)

最突出的编码风格之一是遵循面向对象的范式。为此，现在的重点是编写模块化的代码，增加调试，创建更健壮、可重用的代码。这都鼓励了不同的任务使用不同的函数，因此我们必然会知道函数的某些黑客行为。本文讨论如何打印函数名。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`function.func_name`**

通过使用一个简单的函数属性函数，func_name，人们可以获得函数的名称，因此在测试目的和文档方面非常方便。缺点是这仅适用于 Python2。

```py
# Python code to demonstrate
# way to get function name
# using function.func_name

# initializing function
def GFG():
    return "You just called for success !!"

# printing function name 
# using function.func_name
print("The name of function is : " + GFG.func_name)
```

**Output :**

```py
The name of function is : GFG

```

**方法 2:使用`function.__name__`**

该函数可用作上述函数的替代函数，并已在 Python3 中引入，因为上述方法中提到的函数已在 Python3 中折旧。

```py
# Python code to demonstrate
# way to get function name
# using function.__name__

# initializing function
def GFG():
    return "You just called for success !!"

# printing function name 
# using function.__name__
print("The name of function is : " + GFG.__name__)
```

**Output :**

```py
The name of function is : GFG

```