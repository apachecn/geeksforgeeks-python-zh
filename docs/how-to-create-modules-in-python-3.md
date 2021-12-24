# 如何在 Python 3 中创建模块？

> 原文:[https://www . geesforgeks . org/如何创建 python 中的模块-3/](https://www.geeksforgeeks.org/how-to-create-modules-in-python-3/)

模块只是具有函数、类和变量的 python 代码。任何带有。py 扩展可以作为模块引用。虽然有一些模块可以通过 python 标准库获得，这些模块是通过 python 安装来安装的，但是其他模块可以使用 pip 安装程序来安装，我们也可以创建自己的 python 模块。

在本文中，我们将看到如何用 python 创建模块。

## 编写模块

任何由函数、类、变量组成的 python 代码都可以被称为模块。我们将编写一个简单的模块，包含一个函数、一个类和一个变量。

## 计算机编程语言

```py
# defining a class Age
class Age:                    

    # defining the __init__ method
    def __init__(self, name, years):    
        self.years = years
        self.name = name

    # defining the getAge method
    def getAge(self):                    
        print("The age of " + self.name +" is "+self.years)

# defining the function hello       
def hello():                
  print('hello geeks!')

# creating a string s 
s = 'I love python!'            
```

在上面的模块中，我们定义了一个类“Age”，它有一个 __init__()和 getAge()方法，用于初始化类对象并获取将要传递的对象的 Age，我们还定义了一个函数 hello()，它将打印“hello geeks！”还有一串“我爱蟒蛇！”。

我们将上述模块命名为 mod.py 并保存。

## 导入模块

现在我们将讨论如何导入一个模块，并从其他 python 文件中使用它的各种函数、类和变量。为此，我们将在与 mod.py 相同的目录中创建一个文件 main.py。

我们将使用 import 语句导入模块，并使用如下函数、类和变量:-

### 使用函数

为了使用模块中的函数，我们将首先导入它，然后使用 module_name.function_name()调用该函数。例如，如果我们想在 main.py 中调用 mod.py 的函数 hello()，我们将首先导入 mod.py，然后用 mod.hello()调用它。

## 巨蟒

```py
# importing the module mod.py
import mod         

# calling the function hello() from mod.py
mod.hello() 
```

**输出:**

```py
hello geeks!
```

**注意:**请确保 main.py 和 mod.py 在同一个目录下。

我们也可以只从模块中导入一个单独的函数来使用它，方法是编写:from module _ name import function _ name

然后直接调用。例如，如果我们想使用上述方法在 main.py 中调用 mod.py 的函数 hello()，我们将在 main.py 中编写以下代码:

## 【Python】

```py
# importing only the function hello from the module mod.py
from mod import hello         

# calling the function hello() 
hello()     
```

**输出:**

```py
hello geeks!
```

### 使用类

我们可以使用这些类通过 module_name.class_name()来创建各种对象。例如，如果我们想在 main.py 中创建一个名为“年龄”的对象，我们将在 main.py 中编写以下代码:

## 【Python】

```py
# importing the module mod.py
import mod          

# creating a object jack with jack as name and 21 as age
jack = mod.Age('jack','21') 

# calling the getAge() method for object 'jack'
jack.getAge()                
```

**输出:**

```py
The age of jack is 21
```

我们只导入特定函数的方式与我们只导入特定类的方式相同。这个的代码将是:

## 【蟒蛇】

```py
# importing only the Age class from mod
from mod import Age          

# creating the object jack with jack as name and 21 as age
jack = Age('jack','21')    

# calling the getAge() method for the object jack
jack.getAge()                
```