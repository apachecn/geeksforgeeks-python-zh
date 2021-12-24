# 如何检查一个对象在 Python 中是否可迭代？

> 原文:[https://www . geeksforgeeks . org/如何在 python 中检查对象是否可迭代/](https://www.geeksforgeeks.org/how-to-check-if-an-object-is-iterable-in-python/)

简单地说，任何可以循环的物体都是可重复的。例如，列表对象是可迭代的，字符串对象也是可迭代的。列表编号和字符串名称是可迭代的，因为我们能够在它们上面循环(在这种情况下使用 for 循环)。在本文中，我们将看到如何检查对象在 Python 中是否可迭代。

**示例:**

> **输入:**“你好”
> 
> **输出:**对象不可迭代
> 
> **解释:**物体可以像(h，e，l，l，o)
> 
> **输入:** 5
> 
> **输出:****“**int”对象不可迭代

**例 1:**

## 蟒蛇 3

```py
# code
name = "Hello"

for letter in name:
  print(letter, end = " ")
```

**输出:**

```py
H e l l o
```

**例 2:**

## 蟒蛇 3

```py
# code
number = 5 
for i in number:
  print(i)
```

**输出**

```py
TypeError: 'int' object is not iterable
```

然而， **int** 对象不是**可迭代的**，浮动对象也是如此。整数对象号不是**可迭代的**，因为我们不能在它上面循环。

#### 检查物体的可重复性

我们将探索检查一个物体是否可重复的不同方法。我们使用 **hasattr()** 函数来测试字符串对象名是否具有 **__iter__** 属性来检查可迭代性。然而，这种检查并不全面。

**方法 1:使用 __iter__ 方法检查。**

## 蟒蛇 3

```py
# code
name = 'Roster'

if hasattr(name, '__iter__'):
  print(f'{name} is iterable')

else:
  print(f'{name} is not iterable')
```

**输出:**

```py
Roster is iterable
```

**方法 2:使用 collections.abc 模块的 Iterable 类。**

我们可以通过检查一个对象是否是 iterable 类的实例来验证它是可迭代的。实例检查使用 iterable 类将字符串对象报告为可正确迭代。这也适用于 Python 3。对于 Python 3.3 及更高版本，您必须从**集合导入 Iterable 类，而不是像这样从集合导入:**

## 蟒蛇 3

```py
# code
from collections.abc import Iterable

name = 'Roster'

if isinstance(name, Iterable):
  print(f"{name} is iterable")

else:
  print(f"{name} is not iterable")
```

**输出:**

```py
Roster is iterable
```

**方法 3:使用 iter()内置函数。**

**iter** 内置函数的工作方式如下:

*   检查对象是否实现了 **__iter__，**并调用它来获取迭代器。
*   如果失败，Python 会引发**类型错误**，通常会说“C 对象不可重复**，**，其中 C 是目标对象的类。

**代码:**

## 蟒蛇 3

```py
# code
name = "Roster"

try:
  iter(name)
  print("{} is iterable".format(name)) 

except TypeError:
  print("{} is not iterable".format(name))
```

**输出:**

```py
Roster is iterable
```