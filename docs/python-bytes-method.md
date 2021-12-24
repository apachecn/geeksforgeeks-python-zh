# Python 字节()方法

> 原文:[https://www.geeksforgeeks.org/python-bytes-method/](https://www.geeksforgeeks.org/python-bytes-method/)

**Python byte()函数**将对象转换为给定大小和数据的不可变字节表示的对象。

> **语法:**字节(src，enc，err)
> 
> **参数:**
> 
> *   **src :** 必须转换的源对象
> *   **enc :** 如果对象是字符串，则需要编码
> *   **err :** 字符串转换失败时处理错误的方法。
> 
> **根据 src 类型返回:**由 unicode 0-256 个字符组成的字节不可变对象。
> 
> *   **整数:**返回大小初始化为空的数组
> *   **可迭代:**返回可迭代大小的数组，其元素等于可迭代元素(0-256)
> *   **字符串:**返回编码后的字符串 acc。如果编码失败，根据指定的 err 执行操作。
> *   **无参数:**返回大小为 0 的数组。

## Python 字节数()示例

### **示例 1:将字符串转换为字节**

在本例中，我们将使用 Python bytes()函数将字符串转换为字节，为此，我们获取一个带有字符串的变量，并将其传递给带有 UTF-8 参数的 bytes()函数。UTF-8 能够使用一到四个一字节的代码单元以 Unicode 编码所有 1，112，064 个有效字符代码点

## 蟒蛇 3

```
# python code demobstrating
# int to bytes
str = "Welcome to Geeksforgeeks"

arr = bytes(str, 'utf-8')

print(arr)
```

**输出:**

```
b'Welcome to Geeksforgeeks'
```

### 示例 **2:来自** **的字节数组一个整数**

在本例中，我们将看到如何使用 Python bytes()函数从整数中获取字节数组，为此，我们将把整数传递给 bytes()函数。

## 蟒蛇 3

```
# python code to demonstrate
# int to bytes

number = 12
result = bytes(number)

print(result)
```

**输出:**

```
b'\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'
```

### **示例 3:空**参数**带字节()**

当我们传递 noting in bytes()函数时，它会创建一个大小为 0 的数组。

## 蟒蛇 3

```
print(bytes())
```

**输出:**

```
b''
```

### **示例 4:** 演示整数、无和可数上的字节()

## 蟒蛇 3

```
# Python 3 code to demonstrate the
# working of bytes() on int, iterables, none

# initializing integer and iterables
a = 4
lis1 = [1, 2, 3, 4, 5]

# No argument case
print ("Byte conversion with no arguments : " + str(bytes()))

# conversion to bytes
print ("The integer conversion results in : "  + str(bytes(a)))
print ("The iterable conversion results in : "  + str(bytes(lis1)))
```

输出:

```
Byte conversion with no arguments : b''
The integer conversion results in : b'\x00\x00\x00\x00'
The iterable conversion results in : b'\x01\x02\x03\x04\x05'
```

## 字符串字节的行为

**字节接受字符串作为参数，并需要一个编码方案来执行它。其中最重要的方面是在编码失败的情况下处理错误，定义的一些错误处理方案如下:**

> ****字符串错误处理程序:****
> 
> *   ****严格:**在编码失败的情况下引发默认的 UnicodeDecodeError。**
> *   ****忽略:**忽略不可忽略的字符并编码剩余的字符串。**
> *   ****替换:**用“？”替换不可修改的字符。**

### **使用字符串演示字节()的示例**乐:D****

## **蟒蛇 3**

```
# Python 3 code to demonstrate the
# working of bytes() on string

# initializing string
str1 = 'GeeksfÖrGeeks'

# Giving ascii encoding and ignore error
print("Byte conversion with ignore error : " +
      str(bytes(str1, 'ascii', errors='ignore')))

# Giving ascii encoding and replace error
print("Byte conversion with replace error : " +
      str(bytes(str1, 'ascii', errors='replace')))

# Giving ascii encoding and strict error
# throws exception
print("Byte conversion with strict error : " +
      str(bytes(str1, 'ascii', errors='strict')))
```

****输出:****

```
Byte conversion with ignore error : b'GeeksfrGeeks'
Byte conversion with replace error : b'Geeksf?rGeeks'
```

**例外:**

> **unicode encodererror:“ascii”编解码器无法对位置 6 中的字符“\xd6”进行编码:序数不在范围内(128)**