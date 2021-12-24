# Python 中的 int()函数

> 原文:[https://www.geeksforgeeks.org/python-int-function/](https://www.geeksforgeeks.org/python-int-function/)

**Python int()函数**从给定对象返回一个整数，或将给定基数的数字转换为十进制。

### **Python int()语法:**

> int(字符串，基数)

### **Python int()参数:**

*   **字符串:**由 1 和 0 组成
*   **基数:**(整数值)数字的基数。

### **Python int()返回:**

返回一个整数值，它相当于给定基中的二进制字符串。

### **Python int()异常和错误:**

**类型错误:**当字符串或整数以外的任何数据类型在其等效位置传递时，返回类型错误。

## Python int()方法示例

### **示例 1:在 Python 中使用 int()函数**

## 蟒蛇 3

```
# Python3 program for implementation
# of int() function
num = 13

String = '187'

# Stores the result value of
# binary "187" and num addition
result_1 = int(String) + num
print("int('187') + 13 = ", result_1, "\n")

# Example_2
str = '100'

print("int('100') with base 2 = ", int(str, 2))
print("int('100') with base 4 = ", int(str, 4))
print("int('100') with base 8 = ", int(str, 8))
print("int('100') with base 16 = ", int(str, 16))
```

**输出:**

```
int('187') + 13 =  200 

int('100') with base 2 =  4
int('100') with base 4 =  16
int('100') with base 8 =  64
int('100') with base 16 =  256
```

### 示例 2:将二进制字符串转换为 Python int 基

## 蟒蛇 3

```
# Python3 program for implementation
# of int() function

# "111" taken as the binary string
binaryString = "111"

# Stores the equivalent decimal
# value of binary "111"
Decimal = int(binaryString, 2)

print("Decimal equivalent of binary 111 is", Decimal)

# "101" taken as the octal string
octalString = "101"

# Stores the equivalent decimal
# value of binary "101"
Octal = int(octalString, 8)

print("Decimal equivalent of octal 101 is", Octal)
```

**输出:**

```
Decimal equivalent of binary 111 is 7
Decimal equivalent of octal 101 is 65
```

### **示例 3:** 演示类型错误的程序

## 蟒蛇 3

```
# Python3 program to demonstrate
# error of int() function

# when the binary number is not
# stored in as string
binaryString = 111

# it returns an error for passing an
# integer in place of string
decimal = int(binaryString, 2)

print(decimal)
```

**输出:**

```
TypeError: int() can't convert non-string with explicit base
```

### 示例 4: Python int()异常

## 蟒蛇 3

```
try:
    var = "Geeks"
    print(int(var))
except ValueError as e:
    print(e)
```

**输出:**

> int()的无效文字，基数为 10:【极客】

### **应用:**

它用于所有的**标准转换**。例如二进制到十进制、八进制到十进制、十六进制到十进制的转换。