# 使用 Python 将二进制转换为字符串

> 原文:[https://www . geesforgeks . org/convert-binary-to-string-using-python/](https://www.geeksforgeeks.org/convert-binary-to-string-using-python/)

数据转换一直是广泛使用的实用工具，其中之一可以是转换一个二进制等价于它的字符串。
让我们讨论一下实现这一点的某些方法。
**方法#1:**
简单的方法是将给定的二进制数据转换为十进制，方法是取二进制数字(dn)的和乘以它们的 2*(2^n).幂二进制数据被分成 7 比特组，因为这组二进制数据作为输入，返回相应的十进制值，即字符串字符的 ASCII 码。然后使用 chr()函数将这个 ASCII 码转换成字符串。
**注意:**这里我们对 7 的集合中的二进制数据进行切片，因为原始 ASCII 表是在 7 位上编码的，因此，它有 128 个字符。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Converting binary to string
# Using BinarytoDecimal(binary)+chr()

# Defining BinarytoDecimal() function
def BinaryToDecimal(binary):

    binary1 = binary
    decimal, i, n = 0, 0, 0
    while(binary != 0):
        dec = binary % 10
        decimal = decimal + dec * pow(2, i)
        binary = binary//10
        i += 1
    return (decimal)   

# Driver's code
# initializing binary data
bin_data ='10001111100101110010111010111110011'

# print binary data
print("The binary value is:", bin_data)

# initializing a empty string for
# storing the string data
str_data =' '

# slicing the input and converting it
# in decimal and then converting it in string
for i in range(0, len(bin_data), 7):

    # slicing the bin_data from index range [0, 6]
    # and storing it as integer in temp_data
    temp_data = int(bin_data[i:i + 7])

    # passing temp_data in BinarytoDecimal() function
    # to get decimal value of corresponding temp_data
    decimal_data = BinaryToDecimal(temp_data)

    # Decoding the decimal value returned by
    # BinarytoDecimal() function, using chr()
    # function which return the string corresponding
    # character for given ASCII value, and store it
    # in str_data
    str_data = str_data + chr(decimal_data)

# printing the result
print("The Binary value after string conversion is:",
       str_data)
```

**输出:**

```py
The binary value is: 10001111100101110010111010111110011
The Binary value after string conversion is:  Geeks
```

**方法 2:** 使用 int()函数
每当 int()函数有两个参数时，它都会告诉 int()函数第二个参数是输入字符串的基。如果输入字符串大于 10，那么 Python 假设下一个数字序列来自 ABCD。因此，这个概念可以用于将二进制序列转换为字符串。下面是实现。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Converting binary to string
# Using BinarytoDecimal(binary)+chr()

# Defining BinarytoDecimal() function
def BinaryToDecimal(binary):

    # Using int function to convert to
    # string  
    string = int(binary, 2)

    return string

# Driver's code
# initializing binary data
bin_data ='10001111100101110010111010111110011'

# print binary data
print("The binary value is:", bin_data)

# initializing a empty string for
# storing the string data
str_data =' '

# slicing the input and converting it
# in decimal and then converting it in string
for i in range(0, len(bin_data), 7):

    # slicing the bin_data from index range [0, 6]
    # and storing it in temp_data
    temp_data = bin_data[i:i + 7]

    # passing temp_data in BinarytoDecimal() function
    # to get decimal value of corresponding temp_data
    decimal_data = BinaryToDecimal(temp_data)

    # Decoding the decimal value returned by
    # BinarytoDecimal() function, using chr()
    # function which return the string corresponding
    # character for given ASCII value, and store it
    # in str_data
    str_data = str_data + chr(decimal_data)

# printing the result
print("The Binary value after string conversion is:",
       str_data)
```

**输出:**

```py
The binary value is: 10001111100101110010111010111110011
The Binary value after string conversion is:  Geeks
```