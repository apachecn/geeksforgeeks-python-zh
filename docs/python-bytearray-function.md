# Python | bytearray()函数

> 原文:[https://www.geeksforgeeks.org/python-bytearray-function/](https://www.geeksforgeeks.org/python-bytearray-function/)

`**bytearray()**`方法返回一个 bytearray 对象，它是一个给定字节的数组。它给出了一个可变的整数序列，范围为 0 < = x < 256。

**语法:**

```
bytearray(source, encoding, errors)
```

**参数:**

```
source*[optional]*: Initializes the array of bytes
encoding*[optional]*: Encoding of the string
errors*[optional]*: Takes action when encoding fails

```

**返回:**返回给定大小的字节数组。

***源*** 参数可以用几种不同的方式初始化数组。让我们借助例子逐一讨论。

**代码#1:** 如果字符串必须提供编码和错误参数，`**bytearray()**`使用`str.encode()`将字符串转换为字节

```
str = "Geeksforgeeks"

# encoding the string with unicode 8 and 16
array1 = bytearray(str, 'utf-8')
array2 = bytearray(str, 'utf-16')

print(array1)
print(array2)
```

**输出:**

```
bytearray(b'Geeksforgeeks')
bytearray(b'\xff\xfeG\x00e\x00e\x00k\x00s\x00f\x00o\x00r\x00g\x00e\x00e\x00k\x00s\x00')
```

**代码#2:** 如果是整数，创建一个该大小的数组，并用空字节初始化。

```
# size of array
size = 3

# will create an array of given size 
# and initialize with null bytes
array1 = bytearray(size)

print(array1)
```

**输出:**

```
bytearray(b'\x00\x00\x00')
```

**代码#3:** 如果一个对象，只读缓冲区将被用来初始化字节数组。

```
# Creates bytearray from byte literal
arr1 = bytearray(b"abcd")

# iterating the value
for value in arr1:
    print(value)

# Create a bytearray object
arr2 = bytearray(b"aaaacccc")

# count bytes from the buffer
print("Count of c is:", arr2.count(b"c"))
```

**输出:**

```
97
98
99
100
Count of c is: 4
```

**代码# 4:**If Iterable(范围 0 < = x < 256)，用作数组的初始内容。

```
# simple list of integers
list = [1, 2, 3, 4]

# iterable as source
array = bytearray(list)

print(array)
print("Count of bytes:", len(array))
```

**输出:**

```
bytearray(b'\x01\x02\x03\x04')
Count of bytes: 4
```

**代码#5:** 如果没有源，则创建大小为 0 的数组。

```
# array of size o will be created

# iterable as source
array = bytearray()

print(array)
```

**输出:**

```
bytearray(b'')
```