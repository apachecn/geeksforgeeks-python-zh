# Python | Float 类型及其方法

> 原文:[https://www . geesforgeks . org/python-float-type-and-its-methods/](https://www.geeksforgeeks.org/python-float-type-and-its-methods/)

Python 中的 **`float`** 类型代表浮点数。浮点用于表示实数，用小数点来划分整数和小数部分。例如，97.98、32.3+e18、-32.54e100 都是浮点数。

Python 浮点值表示为 64 位双精度值。任何浮点数的最大值大约为 1.8 x 10 <sup>308</sup> 。任何大于这个数的数字都会用 Python 中的字符串`inf` 来表示。

```py
# Python code to demonstrate float values.

print(1.7e308)

# greater than 1.8 * 10^308
# will print 'inf'
print(1.82e308)
```

**输出:**

```py
1.7e+308
inf
```

浮点数在计算机硬件中表示为 2 进制分数。例如，十进制分数 0.125 的值为 1/10 + 2/100 + 5/1000，同样，二进制分数 0.001 的值为 0/2 + 0/4 + 1/8。这两个分数具有相同的值，唯一真正的区别是第一个分数用 10 为基数的分数表示法书写，第二个分数用 2 为基数。
不幸的是，大多数十进制分数不能精确地表示为二进制分数。结果是，一般来说，您输入的十进制浮点数只能由机器中实际存储的二进制浮点数来近似。

`float` 类型实现了`numbers.Real`抽象基类。返回一个转换为浮点数的表达式。`float` 还有以下附加方法:

**[float . as _ integer _ ratio():](https://www.geeksforgeeks.org/as_integer_ratio-python-reduced-fraction-given-rational/)**返回一对整数，其比率正好等于实际的具有正分母的 float。在无穷小的情况下，它会引发溢出错误和值错误。

```py
# Python3 program to illustrate
# working of float.as_integer_ratio()

def frac(d):

    # Using as_integer_ratio
    b = d.as_integer_ratio() 

    return b 
# Driver code
if __name__=='__main__':
    b = frac(3.5) 
    print(b[0], "/", b[1])
```

**输出:**

```py
7 / 2

```

**float.is_integer() :** 如果 float 实例是有限的整数值，则返回 True，否则返回 False。

```py
# Python3 program to illustrate
# working of float.is_integer()

def booln():

    # using is_integer
    print((-5.0).is_integer())
    print((4.8).is_integer())
    print(float.is_integer(275.0))

# Driver code
if __name__=='__main__':
    booln()
```

**输出:**

```py
True
False
True

```

**[float.hex() :](https://www.geeksforgeeks.org/python-hex-function/)** 以十六进制字符串形式返回浮点数的表示形式。

```py
# Python3 program to illustrate
# working of float.hex()

def frac(a): 

    # using float.hex()
    a = float.hex(35.0)

    return a 
# Driver code
if __name__=='__main__':
    b = frac(35.0) 
    print(b)
```

**输出:**

```py
'0x1.1800000000000p+5'

```

**float.fromhex(s) :** 返回由十六进制字符串 s 表示的浮点数。字符串 s 可能有前导空格和尾随空格。

```py
# Python3 program to illustrate
# working of float.fromhex()

def frac(a):

    # using a float.fromhex()
    a = float.fromhex('0x1.1800000000000p+5')

    return a

# Driver code    
if __name__=='__main__':
    b = frac('0x1.1800000000000p+5') 
    print(b)
```

**输出:**

```py
35.0

```

**注意:** float.hex()是实例方法，但是 float.fromhex()是类方法。