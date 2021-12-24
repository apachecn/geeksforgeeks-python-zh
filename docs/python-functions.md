# Python 函数

> 原文:[https://www.geeksforgeeks.org/python-functions/](https://www.geeksforgeeks.org/python-functions/)

**Python 函数**是一组相关语句，旨在执行计算、逻辑或评估任务。这个想法是将一些通常或重复完成的任务放在一起，并创建一个函数，这样我们就可以一次又一次地重复使用包含在其中的代码，而不是为不同的输入编写相同的代码。

函数可以是内置的，也可以是用户定义的。它有助于程序简洁、不重复、有条理。

**语法:**

```
def function_name(parameters):
    """docstring"""
    statement(s)
    return expression
```

## **创建功能**

我们可以使用 **def** 关键字创建一个 Python 函数。

### 示例:Python 创建函数

## 蟒蛇 3

```
# A simple Python function

def fun():
  print("Welcome to GFG")
```

## 调用函数

在创建一个函数之后，我们可以通过使用函数的名称后跟包含该特定函数参数的括号来调用它。

### 示例:Python 调用函数

## 蟒蛇 3

```
# A simple Python function

def fun():
  print("Welcome to GFG")

# Driver code to call a function
fun()
```

**Output**

```
Welcome to GFG
```

## 函数的参数

参数是传递到函数括号内的值。一个函数可以有任意数量的由逗号分隔的参数。

### 示例:带参数的 Python 函数

在本例中，我们将创建一个简单的函数来检查作为参数传递给函数的数字是偶数还是奇数。

## 蟒蛇 3

```
# A simple Python function to check
# whether x is even or odd

def evenOdd(x):
    if (x % 2 == 0):
        print("even")
    else:
        print("odd")

# Driver code to call the function
evenOdd(2)
evenOdd(3)
```

**Output**

```
even
odd
```

## 参数的类型

Python 支持各种类型的参数，这些参数可以在函数调用时传递。让我们详细讨论每种类型。

### [**默认参数**](https://www.geeksforgeeks.org/default-arguments-in-python/)

默认参数是一个参数，如果函数调用中没有为该参数提供值，则该参数采用默认值。以下示例说明了默认参数。

## 蟒蛇 3

```
# Python program to demonstrate
# default arguments

def myFun(x, y=50):
    print("x: ", x)
    print("y: ", y)

# Driver code (We call myFun() with only
# argument)
myFun(10)
```

**Output**

```
('x: ', 10)
('y: ', 50)
```

像 C++默认参数一样，函数中的任意数量的参数都可以有默认值。但是一旦我们有了一个默认参数，它右边的所有参数也必须有默认值。

### **关键词参数**

其思想是允许调用者用值指定参数名，这样调用者就不需要记住参数的顺序。

## 蟒蛇 3

```
# Python program to demonstrate Keyword Arguments
def student(firstname, lastname):
    print(firstname, lastname)

# Keyword arguments
student(firstname='Geeks', lastname='Practice')
student(lastname='Practice', firstname='Geeks')
```

**Output**

```
('Geeks', 'Practice')
('Geeks', 'Practice')
```

### [可变长度参数](https://www.geeksforgeeks.org/args-kwargs-python/)

在 Python 中，我们可以使用特殊符号向函数传递可变数量的参数。有两种特殊的符号:

*   *参数(非关键字参数)
*   **kwargs(关键字参数)

### **示例 1:** 可变长度非关键词参数

## 计算机编程语言

```
# Python program to illustrate
# *args for variable number of arguments

def myFun(*argv):
    for arg in argv:
        print(arg)

myFun('Hello', 'Welcome', 'to', 'GeeksforGeeks')
```

**Output**

```
Hello
Welcome
to
GeeksforGeeks
```

### **示例 2:可变长度关键字参数**

## 蟒蛇 3

```
# Python program to illustrate
# *kwargs for variable number of keyword arguments

def myFun(**kwargs):
    for key, value in kwargs.items():
        print("%s == %s" % (key, value))

# Driver code
myFun(first='Geeks', mid='for', last='Geeks')
```

**Output**

```
first == Geeks
mid == for
last == Geeks
```

## Docstring

函数后的第一个字符串称为文档字符串或[文档字符串](https://www.geeksforgeeks.org/python-docstrings/)。这用于描述函数的功能。在函数中使用 docstring 是可选的，但它被认为是一种好的做法。

以下语法可用于打印出函数的文档字符串:

```
Syntax: print(function_name.__doc__)
```

### **示例:在函数中添加文档字符串**

## 蟒蛇 3

```
# A simple Python function to check
# whether x is even or odd

def evenOdd(x):
    """Function to check if the number is even or odd"""

    if (x % 2 == 0):
        print("even")
    else:
        print("odd")

# Driver code to call the function
print(evenOdd.__doc__)
```

**Output**

```
Function to check if the number is even or odd
```

## 退货声明

函数 return 语句用于退出函数并返回函数调用方，并将指定的值或数据项返回给调用方。

```
Syntax: return [expression_list]
```

return 语句可以由变量、表达式或常量组成，这些变量、表达式或常量在函数执行结束时返回。如果 return 语句中不存在上述任何内容，则返回无对象。

### 示例:Python 函数返回语句

## 蟒蛇 3

```
def square_value(num):
    """This function returns the square
    value of the entered number"""
    return num**2

print(square_value(2))
print(square_value(-4))
```

**输出:**

```
4
16
```

## Python 函数是按引用传递还是按值传递？

需要注意的一点是，在 Python 中，每个变量名都是一个引用。当我们将一个变量传递给一个函数时，会创建一个对该对象的新引用。Python 中的参数传递和 Java 中的引用传递是一样的。

**示例:**

## 蟒蛇 3

```
# Here x is a new reference to same list lst
def myFun(x):
    x[0] = 20

# Driver Code (Note that lst is modified
# after function call.
lst = [10, 11, 12, 13, 14, 15]
myFun(lst)
print(lst)
```

**Output**

```
[20, 11, 12, 13, 14, 15]
```

当我们传递引用并将接收到的引用更改为其他内容时，传递的参数和接收到的参数之间的连接就会断开。例如，考虑下面的程序。

## 蟒蛇 3

```
def myFun(x):

    # After below line link of x with previous
    # object gets broken. A new object is assigned
    # to x.
    x = [20, 30, 40]

# Driver Code (Note that lst is not modified
# after function call.
lst = [10, 11, 12, 13, 14, 15]
myFun(lst)
print(lst)
```

**Output**

```
[10, 11, 12, 13, 14, 15]
```

另一个例子说明，如果我们分配一个新值(在函数内部)，引用链接就会断开。

## 蟒蛇 3

```
def myFun(x):

    # After below line link of x with previous
    # object gets broken. A new object is assigned
    # to x.
    x = 20

# Driver Code (Note that lst is not modified
# after function call.
x = 10
myFun(x)
print(x)
```

**Output**

```
10
```

**练习:**试猜下面代码的输出。

## 蟒蛇 3

```
def swap(x, y):
    temp = x
    x = y
    y = temp

# Driver code
x = 2
y = 3
swap(x, y)
print(x)
print(y)
```

**Output**

```
2
3
```

## [匿名函数:](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)

在 Python 中，匿名函数意味着函数没有名称。正如我们已经知道的，def 关键字用于定义普通函数，lambda 关键字用于创建匿名函数。详见[本](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)。

## 蟒蛇 3

```
# Python code to illustrate the cube of a number
# using lambda function

def cube(x): return x*x*x

cube_v2 = lambda x : x*x*x

print(cube(7))
print(cube_v2(7))
```

**Output**

```
343
```

## 函数中的 Python 函数

在另一个函数中定义的函数称为内部函数或嵌套函数。嵌套函数能够访问封闭范围的变量。使用内部函数是为了保护它们不受函数之外发生的任何事情的影响。

## 蟒蛇 3

```
# Python program to
# demonstrate accessing of
# variables of nested functions

def f1():
    s = 'I love GeeksforGeeks'

    def f2():
        print(s)

    f2()

# Driver's code
f1()
```

**Output**

```
I love GeeksforGeeks
```

#### **快速链接:**

*   [Python 函数测验](https://www.geeksforgeeks.org/functions-python-gq/)
*   [Python 中方法和函数的区别](https://www.geeksforgeeks.org/difference-method-function-python/)
*   [Python 中的一级函数](https://www.geeksforgeeks.org/first-class-functions-python/)
*   [最近关于 Python 函数的文章](https://www.geeksforgeeks.org/tag/python-functions/)。