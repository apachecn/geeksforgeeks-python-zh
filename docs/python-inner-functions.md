# Python 内部函数

> 原文:[https://www.geeksforgeeks.org/python-inner-functions/](https://www.geeksforgeeks.org/python-inner-functions/)

在 Python 中，函数被视为第一类对象。语言中的第一类对象始终统一处理。它们可以存储在数据结构中，作为参数传递，或者用在控制结构中。如果一种编程语言将函数视为第一类对象，则称其支持第一类函数。Python 支持第一类函数的概念。

**一级函数的性质:**

*   函数是对象类型的一个实例。
*   您可以将函数存储在变量中。
*   您可以将函数作为参数传递给另一个函数。
*   您可以从函数返回函数。
*   您可以将它们存储在数据结构中，如哈希表、列表等

**注意:**想了解更多一级物体[点击这里](https://www.geeksforgeeks.org/first-class-functions-python/)。

## 内部函数

在另一个函数中定义的函数称为`inner function`或`nested functio` n。嵌套函数能够访问封闭范围的变量。使用内部函数是为了保护它们不受函数之外发生的任何事情的影响。这个过程也被称为`Encapsulation`。要了解更多关于封装[的信息，请点击此处](https://www.geeksforgeeks.org/encapsulation-in-python/)。

**示例:**

```
# Python program to illustrate 
# nested functions 
def outerFunction(text): 
    text = text 

    def innerFunction(): 
        print(text) 

    innerFunction() 

if __name__ == '__main__': 
    outerFunction('Hey !') 
```

**输出:**

```
Hey!

```

在上面的例子中，innerFunction()被定义在 outerFunction()内部，使其成为一个内部函数。要调用 innerFunction()，我们必须首先调用 outerFunction()。然后，外部函数()将继续调用内部函数()，因为它已经在内部定义过了。

重要的是必须调用外部函数，以便内部函数可以执行。为了证明这一点，考虑下面的例子:
**例子:**

```
# Python program to illustrate 
# nested functions 
def outerFunction(text): 
    text = text 

    def innerFunction(): 
        print(text) 

    innerFunction() 
```

**输出:**

```
This code will return nothing when executed.

```

## 嵌套函数中变量的范围

我们可以找到一个变量并在需要时访问它的位置叫做变量的作用域。
已知如何访问函数内部的[全局变量](https://www.geeksforgeeks.org/global-local-variables-python/)，但是，访问外部函数的变量呢？让我们看一个例子:

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

**输出:**

```
I love GeeksforGeeks

```

在上面的例子中，可以看到它类似于从函数访问全局变量。现在假设你想改变外部函数的变量。

```
# Python program to 
# demonstrate accessing of
# variables of nested functions

def f1():
    s = 'I love GeeksforGeeks'

    def f2():
        s = 'Me too'
        print(s)

    f2()
    print(s)

# Driver's code
f1()
```

**输出:**

```
Me too
I love GeeksforGeeks

```

可以看出外函数的变量值没有改变。但是，外部函数的变量值可以改变。有不同的方法可以改变外部函数的变量值。

*   Using an iterable –

    ```
    # Python program to 
    # demonstrate accessing of
    # variables of nested functions

    def f1():
        s = ['I love GeeksforGeeks']

        def f2():
            s[0] = 'Me too'
            print(s)

        f2()
        print(s)

    # Driver's code
    f1()
    ```

    **输出:**

    ```
    ['Me too']
    ['Me too']

    ```

*   Using nonlocal keyword –

    ```
    # Python program to 
    # demonstrate accessing of
    # variables of nested functions

    def f1():
        s = 'I love GeeksforGeeks'

        def f2():
            nonlocal s
            s = 'Me too'
            print(s)

        f2()
        print(s)

    # Driver's code
    f1()
    ```

    **输出:**

    ```
    Me too
    Me too

    ```

*   Value can also be changed as shown in the below example.

    ```
    # Python program to 
    # demonstrate accessing of
    # variables of nested functions

    def f1():
        f1.s = 'I love GeeksforGeeks'

        def f2():
            f1.s = 'Me too'
            print(f1.s)

        f2()
        print(f1.s)

    # Driver's code
    f1()
    ```

    **输出:**

    ```
    Me too
    Me too

    ```

## Python 闭包

闭包是一个函数对象，即使内存中没有值，它也会记住封闭作用域中的值。

*   它是一个存储函数和环境的记录:将函数的每个自由变量(在本地使用，但在封闭范围内定义的变量)与创建闭包时名称绑定到的值或引用相关联的映射。
*   闭包与普通函数不同，它允许函数通过闭包的值或引用副本来访问这些捕获的变量，即使函数在它们的作用域之外被调用。
    过滤器 _ 无。

```
# Python program to illustrate 
# closures 
def outerFunction(text): 
    text = text 

    def innerFunction(): 
        print(text) 

    return innerFunction # Note we are returning function WITHOUT parenthesis 

if __name__ == '__main__': 
    myFunction = outerFunction('Hey !') 
    myFunction() 
```

**输出:**

```
Hey!

```

*   从上面的代码可以看出，闭包有助于调用其范围之外的函数。
*   函数 innerFunction 的作用域只在 outerFunction 内部。但是通过使用闭包，我们可以很容易地扩展它的范围来调用它范围之外的函数。

```
# Python program to illustrate 
# closures 
import logging 
logging.basicConfig(filename ='example.log', level = logging.INFO) 

def logger(func): 
    def log_func(*args): 
        logging.info( 
            'Running "{}" with arguments {}'.format(func.__name__, args)) 
        print(func(*args)) 
    # Necessary for closure to work (returning WITHOUT parenthesis) 
    return log_func               

def add(x, y): 
    return x + y 

def sub(x, y): 
    return x-y 

add_logger = logger(add) 
sub_logger = logger(sub) 

add_logger(3, 3) 
add_logger(4, 5) 

sub_logger(10, 5) 
sub_logger(20, 10) 
```

**输出:**

```
6
9
5
10

```