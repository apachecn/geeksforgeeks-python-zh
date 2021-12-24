# Python 中的 chr()

> 原文:[https://www.geeksforgeeks.org/chr-in-python/](https://www.geeksforgeeks.org/chr-in-python/)

**chr()** 方法返回一个字符串，该字符串表示 Unicode 码位为整数的字符。
**语法:**

```
chr(num)
num : integer value

```

*   chr()方法只接受一个整数作为参数。
*   范围可以从 0 到 1，1141，111(基数 16 为 0x10FFFF)不等。
*   chr()方法返回一个 unicode 点为 num(整数)的字符。
*   如果传递的整数超出了范围，则该方法返回一个 ValueError。

例如:假设我们想打印“通用电气公司，通用电气公司，通用电气公司”。

```
# Python program to illustrate 
# chr() builtin function

print(chr(71), chr(101),
chr(101), chr(107),
chr(115), chr(32),
chr(102), chr(111),
chr(114),chr(32),
chr(71), chr(101),
chr(101), chr(107), 
chr(115))
```

输出:

```
G e e k s   f o r   G e e k s

```

另一个例子:

```
# Python program to illustrate 
# chr() builtin function

numbers = [17, 38, 79]

for number in numbers:

    # Convert ASCII-based number to character.
    letter = chr(number)
    print("Character of ASCII value", number, "is ", letter)
```

输出:

```
Character of ASCII value 17 is  
Character of ASCII value 38 is  &
Character of ASCII value 79 is  O
```

**如果我们给出超出范围的东西会发生什么？**

```
# Python program to illustrate 
# chr() builtin function
# if value given is 
# out of range

# Convert ASCII-based number to character
print(chr(400))
```

输出:

```
No Output

```

我们不会得到任何输出，编译器会抛出一个错误:

```
Traceback (most recent call last):
  File "/home/484c76fb455a624cc137946a244a9aa5.py", line 1, in 
    print(chr(400))
UnicodeEncodeError: 'ascii' codec can't encode character 
'\u0190' in position 0: ordinal not in range(128)

```