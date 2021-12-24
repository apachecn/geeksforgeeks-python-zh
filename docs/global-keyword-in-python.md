# Python 中的全局关键字

> 原文:[https://www.geeksforgeeks.org/global-keyword-in-python/](https://www.geeksforgeeks.org/global-keyword-in-python/)

全局关键字是允许用户修改当前范围之外的变量的关键字。它用于从非全局范围(即函数内部)创建[全局变量](https://www.geeksforgeeks.org/global-local-variables-python/)。Global 关键字仅在我们想要进行赋值或想要更改变量时才在函数中使用。打印和访问不需要全局。

**全局关键字规则:**

*   如果一个变量在函数体中的任何地方被赋值，除非显式声明为全局变量，否则它被认为是局部变量。
*   仅在函数内部引用的变量是隐式全局变量。
*   我们使用全局关键字在函数中使用全局变量。
*   不需要在函数外使用全局关键字。

**使用全局关键字:**
要访问函数内部的全局变量，不需要使用全局关键字。
**例 1:**

```py
# Python program showing no need to
# use global keyword for accessing
# a global value

# global variable
a = 15
b = 10

# function to perform addition
def add():
    c = a + b
    print(c)

# calling a function
add()
```

**输出:**

```py

25

```

如果我们需要给一个全局变量赋值，那么我们可以通过将变量声明为全局变量来实现。
**代码 2:** 无全局关键字

```py
# Python program showing to modify
# a global value without using global
# keyword

a = 15

# function to change a global value
def change():

    # increment value of a by 5
    a = a + 5 
    print(a)

change()
```

**输出:**

```py
UnboundLocalError: local variable 'a' referenced before assignment

```

这个输出是一个错误，因为我们试图给外部范围内的变量赋值。这可以通过使用**全局**变量来实现。
**代码 3 :** 带全局关键字

```py
# Python program to modify a global
# value inside a function

x = 15
def change():

    # using a global keyword
    global x

    # increment value of a by 5
    x = x + 5 
    print("Value of x inside a function :", x)
change()
print("Value of x outside a function :", x)
```

**输出:**

```py
Value of x inside a function : 20
Value of x outside a function : 20

```

在上例中，我们首先将 x 定义为函数`change()`内部的全局关键字。然后 x 的值增加 5，即。x=x+5，因此输出为 20。
我们通过改变函数`change()`内部的值可以看到，这个变化也体现在全局变量外部的值上。

**跨 python 模块的全局变量:**
在同一个程序内跨不同模块共享全局变量的最佳方式是创建一个特殊的模块(通常命名为 config 或 cfg)。在应用程序的所有模块中导入配置模块；然后，该模块作为全局名称变得可用。每个模块只有一个实例，因此对模块对象所做的任何更改都会在任何地方得到反映。例如，跨模块共享全局变量
**代码 1:** 创建一个`config.py`文件来存储全局变量:

```py
x = 0
y = 0
z ="none"
```

**代码 2:** 创建 `modify.py`文件修改全局变量:

```py
import config
config.x = 1
config.y = 2
config.z ="geeksforgeeks"
```

这里我们修改了 x、y 和 z 的值。这些变量是在模块`config.py`中定义的，因此我们必须导入`config`模块，并且我们可以使用`config.variable_name`来访问这些变量。
**代码 3:** 创建`main.py`文件修改全局变量:

```py
import config
import modify
print(config.x)
print(config.y)
print(config.z)
```

**输出:**

```py
1
2
geeksforgeeks

```

**嵌套函数中的全局**
为了在嵌套函数中使用全局，我们必须在嵌套函数中声明一个带有全局关键字的变量

```py
# Python program showing a use of
# global in nested function

def add():
     x = 15

     def change():
         global x
         x = 20
     print("Before making changing: ", x)
     print("Making change")
     change()
     print("After making change: ", x)

add()
print("value of x",x)
```

**输出:**

```py
Before making changing:  15
Making change
After making change:  15
value of x 20

```

在上例中，在进行更改之前和之后()，变量`x`取局部变量的值，即 x = 15。在`add()`函数之外，变量`x`将取`change()`函数中定义的值，即 x = 20。因为我们已经在`x`中使用了全局关键字来创建 change()函数(局部范围)中的全局变量。