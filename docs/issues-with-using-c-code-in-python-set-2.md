# 在 Python 中使用 C 代码的问题|第 2 集

> 原文:[https://www . geesforgeks . org/issues-with-use-c-code-in-python-set-2/](https://www.geeksforgeeks.org/issues-with-using-c-code-in-python-set-2/)

先决条件:[在 Python 中使用 C 代码的问题|集合 1](https://www.geeksforgeeks.org/issues-with-using-c-code-in-python-set-1/)

*双数组类型*类可以处理 Python 中数组、numpy 数组、列表、元组等不同形式的情况。在这个类中，定义了一个单一的方法`from_param()`。该方法采用单个参数，并将其缩小到一个兼容的 ctypes 对象(在本例中是一个指向`**ctypes.c_double**`的指针)。

在下面的代码中，参数的 typename 被提取出来，并用于分派给一个更专门的方法。例如，如果一个列表被传递，类型名就是列表，调用一个方法`from_list()`。对于列表和元组，`**from_list()**`方法执行到 ctypes 数组对象的转换。

**代码#1 :**

```py
nums = [1, 2, 3]
a = (ctypes.c_double * len(nums))(*nums)
print ("a : ", a)

print ("\na[0] : ", a[0])

print ("\na[1] : ", a[1])

print ("\na[2] : ", a[2])
```

**输出:**

```py
a : <__main__.c_double_Array_3 object at 0x10069cd40>

a[0] : 1.0

a[1] : 2.0

a[2] : 3.0

```

`**from_array()**` 方法提取底层内存指针，并将其转换为数组对象的 ctypes 指针对象。

**代码#2 :**

```py
import array
arr = array.array('d', [1, 2, 3])
print ("arr : ", arr)

ptr_ = a.buffer_info()
print ("\nptr :", ptr)

print ("\n", ctypes.cast(ptr, ctypes.POINTER(ctypes.c_double)))
```

**输出:**

```py
arr : array('d', [1.0, 2.0, 3.0])

ptr : 4298687200

<__main__.LP_c_double object at 0x10069cd40> 

```

`**from_ndarray()**`显示了 numpy 阵列的可比转换代码。通过定义 ***双数组类型*** 类并将其用于`avg()`的类型签名中，该函数可以接受各种不同的类似数组的输入。

**代码#3 :**

```py
# libraries
import sample
import array
import numpy

print("Average of list : ", sample.avg([1, 2, 3]))

print("\nAverage of tuple : ", sample.avg((1, 2, 3)))

print(\nAverage of array : ", sample.avg(array.array('d', [1, 2, 3])))

print(\nAverage of numpy array : ", sample.avg(numpy.array([1.0, 2.0, 3.0])))
```

**输出:**

```py
Average of list : 2.0

Average of tuple : 2.0 

Average of array : 2.0

Average of numpy array : 2.0

```

要使用简单的 C 结构，只需定义一个包含适当字段和类型的类，如下面的代码所示。定义之后，可以使用类型签名中的类以及需要实例化和使用结构的代码中的类。

**代码#4 :**

```py
class Point(ctypes.Structure):
    _fields_ = [('x', ctypes.c_double),
                ('y', ctypes.c_double)]

point1 = sample.Point(1, 2)
point2 = sample.Point(4, 5)

print ("pt1 x : ", point1.x)

print ("\npt1 y : ", point1.y)

print ("\nDistance between pt1 and pt2 : ",
           sample.distance(point1, point2))
```

**输出:**

```py
pt1 x : 1.0

pt1 y : 2.0

Distance between pt1 and pt2 : 4.242640687119285

```