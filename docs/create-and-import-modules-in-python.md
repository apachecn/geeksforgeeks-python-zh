# 在 Python 中创建和导入模块

> 原文:[https://www . geesforgeks . org/创建和导入 python 模块/](https://www.geeksforgeeks.org/create-and-import-modules-in-python/)

在 Python 中，模块是一个包含 Python 语句和定义的独立的 Python 文件，就像一个名为`GFG.py`的文件，可以认为是一个名为`GFG`的模块，可以借助`import statement`导入。然而，人们可能会对模块和包之间的区别感到困惑。包是目录中模块的集合，为模块提供结构和层次。

#### 模块的优势–

*   **可重用性**:使用模块使得代码的可重用性成为现实。
*   **简单性:**模块关注问题的一小部分，而不是关注整个问题。
*   **作用域:**一个单独的命名空间由一个模块定义，有助于避免标识符之间的冲突。

## 创建和导入模块

模块只是一个扩展名为`.py`的 Python 文件，可以导入到另一个 Python 程序中。Python 文件的名称成为模块名称。该模块包含可以在另一个程序中使用的类、变量和函数的定义和实现。

**示例:**让我们创建一个名为 GFG 的简单模块。

```
''' GFG.py '''

# Python program to create
# a module

# Defining a function
def Geeks():
    print("GeeksforGeeks")

# Defining a variable
location = "Noida"
```

上面的例子显示了一个名为 GFG 的简单模块的创建，因为上面的 Python 文件的名称是 GFG.py。当执行这段代码时，它什么也不做，因为创建的函数没有被调用。

要使用上面创建的模块，请在同一目录中创建新的 Python 文件，并使用 import 语句导入 GFG 模块。

**例:**

```
# Python program to demonstrate
# modules

import GFG

# Use the function created
GFG.Geeks()

# Print the variable declared
print(GFG.location)
```

**输出:**

```
GeeksforGeeks
Noida

```

上面的例子展示了一个只有函数和变量的简单模块。现在让我们用类、函数和变量创建一个稍微复杂一点的模块。下面是实现。

**示例:**打开上面创建的 GFG 模块并进行以下更改。

```
''' GFG.py '''

# Python program to demonstrate 
# modules

# Defining a function
def Geeks():
    print("GeeksforGeeks")

# Defining a variable
location = "Noida"

# Defining a class
class Employee():

    def __init__(self, name, position):
        self. name = name
        self.position = position

    def show(self):
        print("Employee name:", self.name)
        print("Employee position:", self.position)
```

在本例中，一个名为 employee 的类已经用 show()方法声明，以打印雇员的详细信息。现在打开 Python 脚本来导入和使用这个模块。

**示例:**

```
# Python program to demonstrate
# modules

import GFG

# Use the class created
emp = GFG.Employee("Nikhil", "Developer")
emp.show()
```

**输出:**

```
Employee name: Nikhil
Employee position: Developer

```

#### 导入所有名称

模块中的所有对象都可以作为变量导入。这可防止将模块名称用作前缀。

**语法:**

```
from module_name_ import *

```

**示例:**我们将使用上面创建的 GFG 模块。

```
# Python program to demonstrate
# modules

from GFG import *

# Calling the function
Geeks()

# Printing the variable
print(location)

# Calling class
emp = Employee("Nikhil", "Developer")
emp.show()
```

**输出:**

```
GeeksforGeeks
Noida
Employee name: Nikhil
Employee position: Developer

```

#### 通过重命名导入

可以用用户指定的另一个名称导入模块。

**例:**

```
# Python program to demonstrate
# modules

import GFG as g

# Calling the function
g.Geeks()

# Printing the variable
print(g.location)

# Calling class
emp = g.Employee("Nikhil", "Developer")
emp.show()
```

**输出:**

```
GeeksforGeeks
Noida
Employee name: Nikhil
Employee position: Developer

```