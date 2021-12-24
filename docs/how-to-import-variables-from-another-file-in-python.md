# 如何在 Python 中从另一个文件导入变量？

> 原文:[https://www . geesforgeks . org/如何从另一个 python 文件导入变量/](https://www.geeksforgeeks.org/how-to-import-variables-from-another-file-in-python/)

当代码行增加时，搜索所需的代码块是很麻烦的。根据工作情况区分代码行是一个很好的做法。这可以通过为不同的工作代码创建单独的文件来实现。我们知道，Python 中的各种库提供了各种方法和变量，我们使用简单的导入<library_name>就可以访问这些方法和变量。比如数学库。如果我们想使用 pi 变量，我们使用 import math，然后是 math.pi。</library_name>

要从另一个文件导入变量，我们必须从当前程序导入该文件。这将提供对该文件中所有可用方法和变量的访问。

## 进口声明

通过在其他 Python 源文件中执行导入语句，我们可以将任何 Python 源文件用作模块。当解释器遇到导入语句时，如果模块出现在搜索路径中，它将导入该模块。搜索路径是解释器在导入模块时搜索的目录列表。

## 来自导入的语句

Python 的 from 语句允许您从模块中导入特定的属性。

**注意:**更多信息请参考 [Python 模块](https://www.geeksforgeeks.org/python-modules/)

不同的**方法**从其他文件导入变量

*   导入<file_name>后使用<file_name>。<variable_name>访问变量</variable_name></file_name></file_name>
*   从<file_name>导入<variable_names>并使用变量</variable_names></file_name>
*   从<file_name>导入*然后直接使用变量。</file_name>

**示例:**

假设我们有一个名为“交换. py”的文件。我们必须将 x 和 y 变量从这个文件导入到另一个名为“calval.py”的文件中。

## 蟒蛇 3

```py
# swaps.py file from which variables to be imported
x = 23
y = 30

def swapVal(x, y):
  x,y = y,x
  return x, y
```

**现在创建第二个 python 文件，从上面的代码中调用变量:**

## 蟒蛇 3

```py
# calval.py file where to import variables
# import swaps.py file from which variables 
# to be imported
# swaps.py and calval.py files should be in 
# same directory.
import swaps

# Import x and y variables using 
# file_name.variable_name notation
new_x = swaps.x
new_y = swaps.y

print("x value: ", new_x, "y value:", new_y)

# Similarly, import swapVal method from swaps file
x , y = swaps.swapVal(new_x,new_y)

print("x value: ", x, "y value:", y)
```

**输出:**

```py
x value:  23 y value: 30
x value:  30 y value: 23
```