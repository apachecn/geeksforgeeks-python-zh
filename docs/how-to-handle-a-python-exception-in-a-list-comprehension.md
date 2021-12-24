# 如何处理列表理解中的 Python 异常？

> 原文:[https://www . geesforgeks . org/如何处理 python 列表中的异常-理解/](https://www.geeksforgeeks.org/how-to-handle-a-python-exception-in-a-list-comprehension/)

[异常](https://www.geeksforgeeks.org/python-exception-handling/)是中断程序流程的东西。这些异常会停止进程运行，并发出一条错误消息。异常可以简单地被视为表示错误的对象。Python 中有预定义的异常和用户定义的异常。在本文中，我们将讨论如何在[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)中处理 Python 异常，但是让我们首先学习什么是列表理解。

## Python 中的列表理解

[列表理解](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)用于从现有列表或 Python 中的任何其他可迭代列表创建新列表。一个可迭代表中的元素被迭代，如果需要，检查某些条件，如果它满足指定的标准，它将被添加到新的可迭代表中。

**语法:**

```
new_list=[variable_name  <for loop>  <if-condition>]
```

在 Python 中，没有特殊的内置方法来处理列表理解中出现的异常。本文包含可用于处理在列表理解中引发的异常的代码片段。

### 预定义的异常处理

让我们看看列表理解中一些预定义的异常处理。

**1)处理零分错误**

考虑两个包含整数的列表(列表 1、列表 2)。现在需要通过将 list1 元素除以 list2 元素来形成一个新的列表(list3)。它可以用下面给出的公式表示。

```
list3 [i] = list1 [i] / list2 [i]
```

将元素向下舍入为 0 时，会引发错误。应该捕获此异常，并显示错误消息。这可以通过编写下面代码片段中给出的实用函数来实现。

## 蟒蛇 3

```
list1 = [2, 6, 41, 1, 58, 33, -7, 90]
list2 = [1, 3, 2, 0, 6, 3, 7, 0]

def util_func(a, b):
    try:
        return round(a/b, 3)
    except ZeroDivisionError as e:
        print("Division by zero not permitted!!!")

list3 = [util_func(x, y) for x, y in zip(list1, list2)]

print(list3)
```

**输出:**

```
Division by zero not permitted!!!
Division by zero not permitted!!!
[2.0, 2.0, 20.5, None, 9.667, 11.0, -1.0, None]
```

在这种情况下，将打印自定义错误消息。

**2)处理值错误**

考虑一个包含整数、字符串格式的整数以及放在一起的单词的列表。现在需要通过单独取数字(字符串和 int 格式)并将其平方来形成一个新的列表。但是在这里，字符串值只需要跳过，不需要打印错误消息。

## 蟒蛇 3

```
li = ['10', '11', 7, 'abc', 'cats', 3, '5']

# helper function
def util_func(a):
    try:
        return int(a)*int(a)
    except ValueError:
        pass

# list comprehension
new_li = [util_func(x) for x in li]

print(new_li)
```

**输出:**

```
[100, 121, 49, None, None, 9, 25]
```

因为我们只是想忽略非数字值，所以我们没有得到任何异常消息，并且在引发异常的地方填充了 **None** 值。

### 用户定义的异常处理

用户定义的异常可以是任何东西，比如该值应该在指定的范围内，或者该值应该可以被某个数字或任何其他东西整除。为此，必须构造一个继承内置异常类的类。然后可以使用助手函数检查异常。考虑下面的例子。

示例 1:考虑一个整数列表[2，43，56，-78，12，51，-29，17，-24]。任务是挑出可被 2 整除的整数，并形成一个新的列表。对于不可分的数字，应在数字上打印错误信息**。**

## 蟒蛇 3

```
# class for user-defined exception handling
class error(Exception):
    def __init__(self, a):
        self.msg = "The number "+str(a)+" is not divisible by 2!!"

# helper function
def util_func(a):
    try:
        if a % 2 != 0:
            raise error(a)
        return(a)
    except error as e:
        print(e.msg)

# input list
li = [2, 43, 56, -78, 12, 51, -29, 17, -24]

# list comprehension to choose numbers
# divisible by 2
new_li = [util_func(x) for x in li]

print("\nThe new list has :", new_li)
```

**输出:**

> 数字 43 不能被 2 整除！！
> 数字 51 不能被 2 整除！！
> 数字-29 不能被 2 整除！！
> 数字 17 不能被 2 整除！！
> 
> 新列表有:[2，无，56，-78，12，无，无，无，-24]

**示例 2:** 从现有列表中形成一个新列表，使所选值介于 10 和 20 之间。

## 蟒蛇 3

```
# class for user-defined exception handling
class error(Exception):
    def __init__(self, a):
        self.msg = "The number "+str(a)+" is not in range!!!"

# helper function
def util_func(a):
    try:
        if a < 10 or a > 20:
            raise error(a)
        return(a)
    except error as e:
        print(e.msg)
        return 0

# input list
li = [11, 16, 43, 89, 10, 14, 1, 43, 12, 21]

# list comprehension to choose numbers
# in range 10 to 20
new_li = [util_func(x) for x in li]

print("\nThe new list has :", new_li)
```

**输出:**

```
The number 43 is not in range!!!
The number 89 is not in range!!!
The number 1 is not in range!!!
The number 43 is not in range!!!
The number 21 is not in range!!!

The new list has : [11, 16, 0, 0, 10, 14, 0, 0, 12, 0]
```