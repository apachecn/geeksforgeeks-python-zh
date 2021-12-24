# Python 中如何将 Float 转换为 Int？

> 原文:[https://www . geesforgeks . org/如何将 python 中的 float 转换为 int/](https://www.geeksforgeeks.org/how-to-convert-float-to-int-in-python/)

将**浮点**值转换为 **int** 是通过 [**类型转换**](https://www.geeksforgeeks.org/type-conversion-python/) 完成的，这是将操作数转换为特定类型的显式方法。然而，要注意的是，这种类型的转换可能倾向于有损转换(数据丢失)。将像 **2** 这样的 int 值转换为浮点将导致 **2.0** ，这种类型的转换是安全的，因为不会丢失数据，但是将 **3.4** 转换为 int 值将导致 **3** 有损转换。
**示例:**

```
Input: 3.3 
Output: 3 

Input: 5.99
Output: 5

```

**方法 1:** 使用 [**int()**](https://www.geeksforgeeks.org/python-int-function/) 进行转换:

要将浮点值转换为 int，我们使用**内置的 int()** 函数，该函数修剪小数点后的值，只返回整数/整数部分。

> **语法:** int(x)
> 
> **返回:**整数值

**例 1:** 类型**浮点数**转换为类型 **int** 的结果。

## 蟒蛇 3

```
# conversion from float to int

num = 9.3

# printing data type of 'num' 
print('type:', 
      type(num).__name__)  

# conversion to int
num = int(num)   

# printing data type of 'num' 
print('converted value:', num, 
      ', type:', type(num).__name__)
```

**输出:**

```
type: float
converted value: 9 , type: int
```

**示例 2:** 在大多数情况下，int()函数会将结果舍入为小于或等于输入的整数，但该行为既不确定也不可预测。一个这样的例子如下所示。

## 蟒蛇 3

```
# example of unpredictable 
# behaviour of int()

num1 = 5.9
num2 = 5.99999999999999999999

num1 = int(num1)
num2 = int(num2)

print(num1, num2, sep = '\n')
```

**输出:**

```
5
6
```

**方法二:**转换使用 [**math.floor()**](https://www.geeksforgeeks.org/python-math-floor-function/) 和 [**math.ceil()**](https://www.geeksforgeeks.org/python-math-ceil-function/) 。

使用 math.floor()函数可以将浮点值转换为不大于输入的 int 值，而使用 math.ceil()函数也可以将其转换为大于输入的最小整数 int 值。为了使用这些方法，需要导入数学模块。

> **语法:**数学. floor(x)
> 
> **参数:**
> 
> **x:** 这是一个数值表达式。
> 
> **返回:**不大于 x 的最大整数。
> 
> **语法:** math.ceil(x)
> 
> **参数:**
> 
> **x:** 这是一个数值表达式。
> 
> **返回:**不小于 x 的最小整数

**示例:**在下面的示例中，使用 floor()和 ceil()方法实现了从 floor 到 int 的转换，前者返回不大于输入的 int，后者返回大于输入的最小整数。

## 蟒蛇 3

```
# conversion using floor and ceil .

# importing math module
import math       

num = 5.6

floor_value = math.floor(num)

ceil_value  = math.ceil(num)

print("the result using floor() : ",
      floor_value , 
      ', type : ',type(floor_value).__name__)

print("the result using ceil()  : ",
      ceil_value,
      ', type: ', type(ceil_value).__name__)
```

**输出:**

```
the result using floor() :  5 , type :  int
the result using ceil()  :  6 , type:  int
```