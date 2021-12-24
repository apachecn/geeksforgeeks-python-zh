# 如何在 Python 中从另一个文件导入一个类？

> 原文:[https://www . geeksforgeeks . org/如何从另一个 python 文件导入类/](https://www.geeksforgeeks.org/how-to-import-a-class-from-another-file-in-python/)

在本文中，我们将看到如何在 Python 中从另一个文件导入一个类。

Python 中的导入类似于 C/C++中的#include header_file。Python 模块可以通过使用 import 导入文件/函数来访问另一个模块的代码。导入声明是调用导入机制的最常见方式，但不是唯一的方式。import 语句由 import 关键字和模块名称组成。

### 入门指南

这里我们创建了一个名为 GFG 的类，它有两个方法:add()和 sub()。除此之外，还在同一个 python 文件中创建了一个名为 method()的显式函数。该文件将作为主 python 文件的模块。

## 计算机编程语言

```
class GFG:

    # methods
    def add(self, a, b):
        return a + b
    def sub(self, a, b):
        return a - b

# explicit function      
def method():
    print("GFG")
```

让上面 python 文件的名称为 **module.py** 。

### 进口

现在是时候导入模块并开始测试我们的新类和函数了。这里，我们将导入一个名为**模块**的模块，并在该模块中创建名为 GFG 的类的对象。现在，我们可以使用它的方法和变量。

## 蟒蛇

```
import module

# Created a class object
object = module.GFG()

# Calling and printing class methods
print(object.add(15,5))
print(object.sub(15,5))

# Calling the function
module.method()
```

**输出:**

```
20
10
GFG
```

如前所述，导入模块会自动将模块中的每个类和性能带入命名空间。如果您只使用一个函数，那么您可以通过只导入该函数来防止名称空间混乱，如下图所示:

## 【Python】

```
# import module
from module import method

# call method from that module  
method()
```

**输出:**

```
GFG
```

这样，我们可以使用类从另一个文件导入。