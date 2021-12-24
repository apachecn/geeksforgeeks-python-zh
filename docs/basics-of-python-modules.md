# Python 模块基础知识

> 原文:[https://www.geeksforgeeks.org/basics-of-python-modules/](https://www.geeksforgeeks.org/basics-of-python-modules/)

一个**库**指的是一个模块的集合，它们一起迎合特定类型的需求或应用。**模块**是文件(。py 文件)包含与特定任务相关的变量、类定义语句和函数。预装 Python 的 Python 模块称为标准库模块。

## 创建我们的模块

我们将创建一个名为 tempConversion.py 的模块，它将 F 值转换为 C 值，反之亦然。

## 蟒蛇 3

```py
# tempConversion.py to convert between
# between Fahrenheit and Centigrade

# function to convert F to C
def to_centigrade(x):
      return 5 * (x - 32) / 9.0

# function to convert C to F
def to_fahrenheit(x):
       return 9 * x / 5.0 + 32

# constants

# water freezing temperature(in Celcius)
FREEZING_C = 0.0  

# water freezing temperature(in Fahrenheit)     
FREEZING_F = 32.0      
```

Now save this python file and the module is created. This module can be used in other programs after importing it.

## 导入模块

在 python 中，为了使用一个模块，它必须被导入。Python 提供了在程序中导入模块的多种方法:

1.  要导入整个模块:

    ```py
    import module_name
    ```

2.  仅导入模块的特定部分:

    ```py
    from module_name import object_name
    ```

3.  导入模块的所有对象:

    ```py
    from module_name import *
    ```

## 使用导入的模块

导入模块后，我们可以按照以下语法使用导入模块的任何函数/定义:

```py
module_name.function_name() 
```

这种引用模块对象的方式称为点标记法。
如果我们使用`from`导入一个函数，使用该函数就不需要提到模块名称和点符号。

**Example 1 :** Importing the whole module :

## 蟒蛇 3

```py
# importing the module
import tempConversion

# using a function of the module
print(tempConversion.to_centigrade(12))

# fetching an object of the module
print(tempConversion.FREEZING_F)
```

**Output :**

```py
-11.11111111111111
32.0

```

**示例 2 :** 导入模块的特定组件:

## 蟒蛇 3

```py
# importing the to_fahrenheit() method
from tempConversion import to_fahrenheit

# using the imported method
print(to_fahrenheit(20))

# importing the FREEZING_C object
from tempConversion import FREEZING_C

# printing the imported variable
print(FREEZING_C)
```

**Output :**

```py
68.0
0.0

```

## Python 标准库函数

python 解释器内置了许多随时可用的功能。要使用 python 的这些内置函数，直接调用函数，如`function_name()`。一些内置的库函数有:input()、int()、float()等

## 蟒蛇 3

```py
num = 5
print("Number entered = ", num)

# oct() converts to octal number-string
onum = oct(num)   

# hex() converts to hexadecimal number-string     
hnum = hex(num)     

print("Octal conversion yields", onum)
print("Hexadecimal conversion yields", hnum)
print(num)
```

**Output :**

```py
Number entered = 5
Octal conversion yields 0o5
Hexadecimal conversion yields 0x5
5

```