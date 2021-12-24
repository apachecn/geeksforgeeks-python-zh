# 给定完整路径如何导入 Python 模块？

> 原文:[https://www . geeksforgeeks . org/如何导入给定完整路径的 python 模块/](https://www.geeksforgeeks.org/how-to-import-a-python-module-given-the-full-path/)

python 模块是一个文件，由 Python 代码和一组函数、类和变量定义组成。该模块使代码可重用且易于理解。需要使用该模块的程序应该导入该特定模块。在本文中，我们将讨论如何在给出完整路径的情况下导入 Python 模块。

有多种方法可以通过使用模块的完整路径来导入模块:

*   使用系统路径追加()函数
*   使用导入库包
*   使用源文件加载器类

考虑以下文件排列，让我们看看如何使用上面列出的方法在 *main.py* 中导入 *gfg.py* 模块:

```py
python
     |--main.py
     |articles
        |--gfg.py  
```

以下是 **gfg.py** 的代码:

## 蟒蛇 3

```py
# class
class GFG:

  # method
  def method_in():
    print("Inside Class method")

# explicit function    
def method_out():
  print("Inside explicit method")
```

## **使用系统路径追加()功能**

这是通过将模块路径添加到路径变量来导入 Python 模块的最简单方法。路径变量包含 Python 解释器查找在源文件中导入的模块的目录。

**语法:**

```py
sys.path.append("module_path")
```

**示例:**

## 蟒蛇 3

```py
# importing module
import sys

# appending a path
sys.path.append('articles')

# importing required module
import gfg
from gfg import GFG

# aceesing its content
GFG.method_in()
gfg.method_out()
```

**输出:**

```py
Inside Class method
Inside explicit method
```

## **使用导入库包**

importlib 包提供了 Python 源代码中的 import 语句的实现，可移植到任何 Python 解释器。这使用户能够创建他们的自定义对象，这有助于他们根据需要使用导入过程。importlib.util 是此包中包含的模块之一，可用于从给定路径导入模块。

**语法:**

> module = import lib . util . spec _ from _ file _ location(" module _ name "，" module_path ")

**示例:**

## 蟒蛇 3

```py
import importlib.util

# specify the module that needs to be 
# imported relative to the path of the 
# module
spec=importlib.util.spec_from_file_location("gfg","articles/gfg.py")

# creates a new module based on spec
foo = importlib.util.module_from_spec(spec)

# executes the module in its own namespace
# when a module is imported or reloaded.
spec.loader.exec_module(foo)

foo.GFG.method_in()
foo.method_out()
```

**输出:**

```py
Inside Class method
Inside explicit method
```

## **使用源文件加载器类**

SourceFileLoader 类是一个抽象基类，用于在实际导入模块的 load_module()函数的帮助下实现源文件加载。

**语法:**

```py
module = SourceFileLoader("module_name","module_path").load_module()
```

**示例:**

## 蟒蛇 3

```py
from importlib.machinery import SourceFileLoader

# imports the module from the given path
foo = SourceFileLoader("gfg","articles/gfg.py").load_module()

foo.GFG.method_in()
foo.method_out()
```

**输出:**

```py
Inside Class method
Inside explicit method
```