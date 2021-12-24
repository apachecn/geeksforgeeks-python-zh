# Python 中的 hex()函数

> 原文:[https://www.geeksforgeeks.org/python-hex-function/](https://www.geeksforgeeks.org/python-hex-function/)

***【hex()***函数是 Python3 中的内置函数之一，用于将一个整数转换为其对应的十六进制形式。

**语法:**

```
hex(x) 
Parameters : 
x - an integer number (*int* object)
Returns :  Returns hexadecimal string.
```

**错误和异常:**

```
TypeError :  Returns TypeError when anything other than
             integer type constants are passed as parameters.
```

**代码#1 :** 说明 *hex()* 功能的使用。

## 蟒蛇 3

```
# Python3 program to illustrate
# hex() function

print("The hexadecimal form of 23 is "
                            + hex(23))

print("The hexadecimal form of the "
      "ascii value is 'a' is " + hex(ord('a')))

print("The hexadecimal form of 3.9 is "
                        + float.hex(3.9))
```

**输出:**

```
The hexadecimal form of 23 is 0x17
The hexadecimal form of the ascii value os 'a' is 0x61
The hexadecimal form of 3.9 is 0x1.f333333333333p+1
```

**代码#2:** 演示浮点值作为参数传递时的类型错误。

## 蟒蛇 3

```
# hex() accepts only integer values as parameters
print("The hexadecimal form of 11.1 is "
                            + hex(11.1))

'''
# The hexadecimal conversion of floating 
# point integers can be done using the
# function float.hex()
print("The hexadecimal form of 11.1 is "
                    + float.hex(11.1))
# Output :
# The hexadecimal form of 11.1 is 0x1.6333333333333p+3

# Similarly, float.hex() throws a TypeError
# when integer values are passed in it.
'''
```

**输出:**

```
Traceback (most recent call last):
  File "/home/7e1ac7e34362fd690cdb72cf294502e1.py", line 2, in 
    print("The hexadecimal form of 11.1 is "+hex(11.1))
TypeError: 'float' object cannot be interpreted as an integer
```

**应用:**
hex()用于所有的**标准转换**。例如十六进制到十进制、十六进制到八进制、十六进制到二进制的转换。

**代码#3 :**

## 蟒蛇 3

```
# TypeConversion from decimal with base 10
# to hexadecimal form with base 16

# Taking input from user
# an integer with base 10
number = int(input("Enter a number with base 10\n"))

# The choices present to the user
print("a. Decimal to Hexadecimal ")
print("b. Decimal to Octal")
print("c. Decimal to Binary")

# taking user input
print("Enter your choice :- ")
choice = input()

# Running a variable choice
# Hexadecimal form if choice
# is set to 'a'
if choice is 'a':

    # lstrip helps remove "0x" from the left
    # rstrip helps remove "L" from the right,
    # L represents a long number
    print("Hexadecimal form of " + str(number) +
        " is " + hex(number).lstrip("0x").rstrip("L"))

if choice is 'b':

    # Octal representation is done
    # by adding a prefix "0o"
    print("Octal form of " + str(number) +
        " is " + oct(number).lstrip("0o").rstrip("L"))

if choice is 'c':

    # Binary representation is done by
    # the addition of prefix "0b"
    print("Binary form of " + str(number) +
        " is "+bin(number).lstrip("0b").rstrip("L"))
```

**输出:**

输入变量 a)

```
Enter a number with base 10
123
a. Decimal to Hexadecimal 
b. Decimal to Octal
c. Decimal to Binary
Enter your choice:- 
a
Hexadecimal form of 123 is 7b
```

输入变量 b)

```
Enter a number with base 10
123456789
a. Decimal to Hexadecimal 
b. Decimal to Octal
c. Decimal to Binary
Enter your choice:- 
a
Hexadecimal form of 123456789 is 75bcd15
```