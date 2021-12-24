# 如何修复:值错误:用序列设置数组元素

> 原文:[https://www . geesforgeks . org/how-fix-value error-用序列设置数组元素/](https://www.geeksforgeeks.org/how-to-fix-valueerror-setting-an-array-element-with-a-sequence/)

在本文中，我们将讨论如何修复 ValueError:使用 Python 用序列设置数组元素。

我们在使用 Numpy 库时基本上遇到的错误是 ValueError:用序列设置数组元素。我们在创建数组或处理 numpy.array 时，基本上都面临这个错误。

发生此错误的原因是 numpy.array 用给定值创建数组，但值的数据类型与提供给 numpy 的数据类型不同。

**防止此错误所需的步骤:**

*   解决这个问题最简单的方法是使用支持所有数据类型的数据类型。
*   解决这个问题的第二种方法是匹配数组的默认数据类型并赋值。

## **方法一:使用常用数据类型**

**示例:**显示错误代码的程序:

## 计算机编程语言

```
# In this program we are demonstrating how different
# Data-type can cause value erro

import numpy

# Creating multi-dimension array
array1 = [1, 2, 4, [5, [6, 7]]]

# Data type of array element
Data_type = int

# This cause Value error
np_array = numpy.array(array1, dtype=Data_type)

print(np_array)
```

**输出:**

> 文件“C:\用户\计算机\下载\he.py”，第 13 行，在
> 
> np_array = numpy.array(array1，dtype = Data _ type)；
> 
> 值错误:用序列设置数组元素。

如果我们为数组的元素提供支持所有数据类型的数据类型，我们可以修复此错误:

**语法:**

```
numpy.array( Array ,dtype = ***Common_DataType*** );
```

**示例:**固定代码

## 计算机编程语言

```
# In this program we fix problem by different data-type

import numpy

# Creating multi-dimension array
array1 = [1, 2, 4, [5, [6, 7]]]

# Object Data type is accept all data-type
Data_type = object

# Now we fix the error
np_array = numpy.array(array1, dtype=Data_type)

print(np_array)
```

**输出:**

```
[1 2 4 list([5, [6, 7]])]
```

## **方法 2:通过匹配值和数组的默认数据类型**

**示例:**显示错误的程序

## 计算机编程语言

```
# In this program we are demonstrating how mismatch
# of data-type can cause value erro

import numpy

# Creating array
array1 = ["Geeks", "For"]

# Default Data type of Array
Data_type = str

np_array = numpy.array(array1, dtype=Data_type)
# This cause error
np_array[1] = ["for", "Geeks"]
print(np_array)
```

**输出:**

> 文件“C:\用户\计算机\下载\he.py”，第 15 行，在
> 
> np_array[1] = ["for "，" Geeks "]；
> 
> 值错误:用序列设置数组元素

在这里，我们已经看到了导致这个错误原因，因为我们将数组作为一个元素分配给接受字符串数据类型的数组。我们可以通过匹配值和数组的数据类型，然后将其作为数组的元素来修复这个错误。

**语法:**

```
if np_array.dtype == type( Variable ):
      expression;
```

**示例:**固定代码

## 计算机编程语言

```
# In this program we fix error by mismatch
# of data-type

import numpy

# Creating array
array1 = ["Geeks", "For"]

# Default Data type of Array
Data_type = str

np_array = numpy.array(array1, dtype=Data_type)

Variable = ["for", "Geeks"]

# First we match the data-type
if np_array.dtype == type(Variable):
    np_array[1] = Variable
else:
    print("Variable value is not the type of numpy array")
print(np_array)
```

**输出:**

```
Variable value is not the type of numpy array
['Geeks' 'For']
```