# __ Python 中的闭包 _ _ 魔法函数

> 原文:[https://www . geesforgeks . org/_ _ closure _ _-python 中的神奇函数/](https://www.geeksforgeeks.org/__closure__-magic-function-in-python/)

Python 中几乎所有的东西都是一个[对象](https://www.geeksforgeeks.org/python-classes-and-objects/)，同样[函数](https://www.geeksforgeeks.org/functions-in-python/)也是一个对象，所有的函数对象都有一个**闭包 __** 属性。__closure__ 是一个 [dunder/magic 函数](https://www.geeksforgeeks.org/dunder-magic-methods-python/#:~:text=Dunder%20or%20magic%20methods%20in%20Python%20are%20the%20methods%20having,commonly%20used%20for%20operator%20overloading.)，即在方法名中有两个下划线作为前缀和后缀的方法

一个 [闭包](https://www.geeksforgeeks.org/python-closures/) 是一个函数对象，它记住封闭范围中的值，即使它们不在内存中。闭包函数的 __closure__ 属性返回一组单元格对象。此单元格对象还有一个名为 cell_contents 的属性，它返回单元格的内容。

**语法:**

```
closure_function.__closure__
```

**例:**

## 蟒蛇

```
# this is a nested function
def gfg(raise_power_to): 

    def power(number): 
       return number ** raise_power_to 
    return power

raise_power_to_3 = gfg(3)
print(raise_power_to_3.__closure__)

print(raise_power_to_3.__closure__[0].cell_contents)
```

**输出:**

> (<0x7f 34 ba 2725 E0 处的单元:0x7f34bde02720 处的 int 对象>)
> 
> 3

在上面的例子中，嵌套函数 *power* 具有与之相关联的 *__closure_* _ 属性，并且它返回一组单元格对象。*单元格 _ 内容*属性返回值 *3* ，因为它是在单元格对象内关闭的。