# Python 按位运算符

> 原文:[https://www.geeksforgeeks.org/python-bitwise-operators/](https://www.geeksforgeeks.org/python-bitwise-operators/)

[运算符](https://www.geeksforgeeks.org/basic-operators-python/)用于对值和变量进行运算。这些是执行算术和逻辑计算的特殊符号。运算符操作的值称为操作数。

> **目录:**
> 
> *   [按位运算符:](#Bitwise_operators)
>     *   [按位与运算符](#Bitwise_AND_operator)
>     *   [按位或运算符](#Bitwise_OR_operator)
>     *   [按位非运算符](#Bitwise_Not_operator)
>     *   [按位异或运算符](#Bitwise_XOR_operator)
> *   [轮班操作员:](#Shift_Operators)
>     *   [按位右移](#Bitwise_right_shift)
>     *   [按位左移](#Bitwise_left_shift)
> *   [按位运算符重载](#Bitwise_Operator_Overloading)

## 按位运算符

在 Python 中，按位运算符用于对整数执行按位计算。整数首先被转换成二进制，然后一点一点地进行运算，因此被称为按位运算符。然后以十进制格式返回结果。

**注意:** Python 按位运算符只对整数起作用。

<figure class="table">

| 操作员 | 描述 | 句法 |
| --- | --- | --- |
| & | 按位“与” | x & y |
| &#124; | 按位“或” | x &#124; y |
| ~ | 按位非 | ~x |
| ^ | 按位异或 | x ^ y |
| >> | 按位右移 | x > > |
| << | 按位左移 | x < < |

</figure>

让我们一个一个地理解每个操作符。
**按位与运算符:**如果两位都是 1，则返回 1，否则返回 0。
**例:**

```py
a = 10 = 1010 (Binary)
b = 4 =  0100 (Binary)

a & b = 1010
         &
        0100
      = 0000
      = 0 (Decimal)
```

**按位或运算符:**如果任一位为 1 或 0，则返回 1。
T3】例:

```py
a = 10 = 1010 (Binary)
b = 4 =  0100 (Binary)

a | b = 1010
         |
        0100
      = 1110
      = 14 (Decimal)
```

**按位非运算符:**返回数字的补码。
T3】例:

```py
a = 10 = 1010 (Binary)

~a = ~1010
   = -(1010 + 1)
   = -(1011)
   = -11 (Decimal)
```

**按位异或运算符:**如果其中一位为 1，另一位为 0，则返回 1，否则返回假。
T3】例:

```py
a = 10 = 1010 (Binary)
b = 4 =  0100 (Binary)

a & b = 1010
         ^
        0100
      = 1110
      = 14 (Decimal)
```

## 蟒蛇 3

```py
# Python program to show
# bitwise operators

a = 10
b = 4

# Print bitwise AND operation
print("a & b =", a & b)

# Print bitwise OR operation
print("a | b =", a | b)

# Print bitwise NOT operation
print("~a =", ~a)

# print bitwise XOR operation
print("a ^ b =", a ^ b)
```

**输出:**

```py
a & b = 0
a | b = 14
~a = -11
a ^ b = 14
```

## 移位运算符

这些运算符用于向左或向右移动一个数的位，从而分别将该数乘以或除以 2。当我们必须将一个数乘以或除以 2 时，它们可以被使用。
**按位右移:**将数字的位右移，结果在左边的空白处填充 0(负数时填充 1)。类似于用 2 的幂除数的效果。
**例:**

```py
Example 1:
a = 10 = 0000 1010 (Binary)
a >> 1 = 0000 0101 = 5

Example 2:
a = -10 = 1111 0110 (Binary)
a >> 1 = 1111 1011 = -5 
```

**按位左移:**将数字的位左移，结果在右边的空白处填充 0。类似于数字乘以 2 的幂的效果。
T3】例:

```py
Example 1:
a = 5 = 0000 0101 (Binary)
a << 1 = 0000 1010 = 10
a << 2 = 0001 0100 = 20 

Example 2:
b = -10 = 1111 0110 (Binary)
b << 1 = 1110 1100 = -20
b << 2 = 1101 1000 = -40 
```

## 蟒蛇 3

```py
# Python program to show
# shift operators

a = 10
b = -10

# print bitwise right shift operator
print("a >> 1 =", a >> 1)
print("b >> 1 =", b >> 1)

a = 5
b = -10

# print bitwise left shift operator
print("a << 1 =", a << 1)
print("b << 1 =", b << 1)
```

**输出:**

```py
a >> 1 = 5
b >> 1 = -5
a << 1 = 10
b << 1 = -20
```

## 按位运算符重载

[操作员过载](https://www.geeksforgeeks.org/operator-overloading-in-python/)意味着给出超出其预定操作含义的扩展含义。例如，运算符+用于添加两个整数，连接两个字符串并合并两个列表。这是可以实现的，因为“+”运算符被 int 类和 str 类重载。您可能已经注意到，相同的内置运算符或函数对不同类的对象显示不同的行为，这被称为**运算符重载**。
下面是按位运算符重载的一个简单示例。

## 蟒蛇 3

```py
# Python program to demonstrate
# operator overloading

class Geek():
    def __init__(self, value):
        self.value = value

    def __and__(self, obj):
        print("And operator overloaded")
        if isinstance(obj, Geek):
            return self.value & obj.value
        else:
            raise ValueError("Must be a object of class Geek")

    def __or__(self, obj):
        print("Or operator overloaded")
        if isinstance(obj, Geek):
            return self.value | obj.value
        else:
            raise ValueError("Must be a object of class Geek")

    def __xor__(self, obj):
        print("Xor operator overloaded")
        if isinstance(obj, Geek):
            return self.value ^ obj.value
        else:
            raise ValueError("Must be a object of class Geek")

    def __lshift__(self, obj):
        print("lshift operator overloaded")
        if isinstance(obj, Geek):
            return self.value << obj.value
        else:
            raise ValueError("Must be a object of class Geek")

    def __rshift__(self, obj):
        print("rshift operator overloaded")
        if isinstance(obj, Geek):
            return self.value & obj.value
        else:
            raise ValueError("Must be a object of class Geek")

    def __invert__(self):
        print("Invert operator overloaded")
        return ~self.value

# Driver's code
if __name__ == "__main__":
    a = Geek(10)
    b = Geek(12)
    print(a & b)
    print(a | b)
    print(a ^ b)
    print(a << b)
    print(a >> b)
    print(~a)
```

**输出:**

```py
And operator overloaded
8
Or operator overloaded
14
Xor operator overloaded
8
lshift operator overloaded
40960
rshift operator overloaded
8
Invert operator overloaded
-11
```

**注意:**要了解更多关于操作员超载[的信息，请点击此处](https://www.geeksforgeeks.org/operator-overloading-in-python/)。