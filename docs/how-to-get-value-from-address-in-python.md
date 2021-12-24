# Python 中如何从地址中获取值？

> 原文:[https://www . geesforgeks . org/如何从 python 中的地址获取价值/](https://www.geeksforgeeks.org/how-to-get-value-from-address-in-python/)

在本文中，我们将讨论如何在 Python 中从地址中获取值。首先，我们要计算变量或 python 对象的内存地址，这可以通过使用 [id()](https://www.geeksforgeeks.org/id-function-python/) 函数来完成。

**语法:**

> id(python_object)

其中，python_object 是任何 python 变量或数据结构，如列表、元组集等。

**示例**:获取特定 python 对象内存地址的 Python 程序

## 蟒蛇 3

```py
#import ctypes
import ctypes

# variable declaration
val = 20

# get the memory address of the python 
# object for variable
print(id(val))

# get the memory address of the python 
# object for list
print(id([1, 2, 3, 4, 5]))

# get the memory address of the python 
# object for tuple
print(id((1, 2, 3, 4, 5)))

# get the memory address of the python 
# object for set
print(id({1, 2, 3, 4, 5}))
```

**输出:**

```py
93937093504096
140292920620368
140292954508752
140292954711056
```

现在我们有了地址，我们可以使用 [ctypes 模块](https://www.geeksforgeeks.org/using-c-codes-in-python-set-2/)再次从内存地址中获取 value/python 对象。

ctypes 代表兼容的数据类型，它允许在 dll 或共享库中调用函数。它可以用来用纯 Python 包装这些库。它用于使用内存地址获取值/Python 对象

**语法:**

> ctypes.cast(memory_address，ctypes.py_object)。价值

哪里，

*   memeory _ address 是变量的内存地址
*   值是用于提取值的方法

**示例 1:** Python 程序从内存地址访问值

## 蟒蛇 3

```py
#import ctypes
import ctypes

# variable declaration
val = 20

# display variable
print("Actual value -", val)

# get the memory address of the python object 
# for variable
x = id(val)

# display memory address
print("Memory address - ", x)

# get the value through memory address
a = ctypes.cast(x, ctypes.py_object).value

# display
print("Value - ", a)
```

**输出:**

```py
Actual value - 20
Memory address -  93937093504096
Value -  20
```

**示例 2:** Python 程序从 Python 数据结构的内存地址中获取值

## 蟒蛇 3

```py
#import ctypes
import ctypes

# variable declaration
val = [1, 2, 3, 4, 5]

# display variable
print("Actual value -", val)

# get the memory address of the python object 
# for variable list
x = id(val)

# display memory address
print("Memory address - ", x)

# get the value through memory address
a = ctypes.cast(x, ctypes.py_object).value

# display
print("Value - ", a)

print("____________________________________")

# variable declaration
val = (1, 2, 3, 4, 5)

# display variable
print("Actual value -", val)

# get the memory address of the python object
# for variable tuple
x = id(val)

# display memory address
print("Memory address - ", x)

# get the value through memory address
a = ctypes.cast(x, ctypes.py_object).value

# display
print("Value - ", a)

print("____________________________________")

# variable declaration
val = {1, 2, 3, 4, 5}

# display variable
print("Actual value -", val)

# get the memory address of the python object 
# for variable set
x = id(val)

# display memory address
print("Memory address - ", x)

# get the value through memory address
a = ctypes.cast(x, ctypes.py_object).value

# display
print("Value - ", a)

print("____________________________________")

# variable declaration
val = {'id': 1, "name": "sravan kumar", "address": "kakumanu"}

# display variable
print("Actual value -", val)

# get the memory address of the python object 
# for variable dictionary
x = id(val)

# display memory address
print("Memory address - ", x)

# get the value through memory address
a = ctypes.cast(x, ctypes.py_object).value

# display
print("Value - ", a)

print("____________________________________")
```

**输出:**

> 实际值–[ 1，2，3，4，5]
> 
> 内存地址–140292824840224
> 
> 值–[ 1，2，3，4，5]
> 
> ____________________________________
> 
> 实际值–( 1，2，3，4，5)
> 
> 内存地址–140292853914128
> 
> 值–( 1，2，3，4，5)
> 
> ____________________________________
> 
> 实际值–{ 1，2，3，4，5}
> 
> 内存地址–140292824862304
> 
> 价值–{ 1，2，3，4，5}
> 
> ____________________________________
> 
> 实际值–{ ' id ':1，' name': 'sravan kumar '，' address': 'kakumanu'}
> 
> 内存地址–140292825009760
> 
> value –{ ' id ':1，' name': 'sravan kumar '，' address': 'kakumanu'}
> 
> ____________________________________