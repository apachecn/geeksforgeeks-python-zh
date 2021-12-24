# Python 中 len()函数的内部工作

> 原文:[https://www . geesforgeks . org/python 中的内部工作函数/](https://www.geeksforgeeks.org/internal-working-of-the-len-function-in-python/)

Python 中的`len()`函数有一个非常特殊的特性，这是人们经常想知道的。在计算可迭代数据结构(字符串、数组、元组等)的长度时，它绝对不需要时间，并且需要相等的时间。)，与数据的大小或类型无关。这显然暗示了`O(1)`的时间复杂性。**但是你有没有想过怎么做？**

Python 遵循的思想是，将长度保持为属性既便宜又易于维护。`len()`实际上是一个调用方法“__len__()”的函数。这个方法是在可迭代数据结构的预定义类中定义的。这个方法实际上充当了一个计数器，它会随着数据的定义和存储而自动递增。因此，当您调用`len()`函数时，您并没有给解释器通过遍历来找到长度的命令，而是要求解释器打印一个已经存储的值。因此，Python 中的`len()`函数以`O(1)`复杂度运行。

因此也可以定义为:

```py
def length(ar):

    # calling the internally 
    # defined __len__() method
    return ar.__len__() 

# Driver code
a = [1, 2, 3, 4]
print(length(a))
```

**输出:**

```py
4

```

**注意:**这可能看起来非常有益，但是请记住，它在数据定义阶段给解释器带来了巨大的负担。这是 Python 在竞争性编程过程中速度较慢的众多原因之一，尤其是在大输入的情况下。