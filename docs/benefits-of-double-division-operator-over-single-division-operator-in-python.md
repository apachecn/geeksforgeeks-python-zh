# Python 中双除法运算符相对于单除法运算符的优势

> 原文:[https://www . geeksforgeeks . org/python 中双除运算符优于单除运算符/](https://www.geeksforgeeks.org/benefits-of-double-division-operator-over-single-division-operator-in-python/)

Python 中的 Double 除法运算符在除法之后返回整数和浮点参数的底值。

```
# A Python program to demonstrate use of  
# "//" for both integers and floating points

print(5//2)
print(-5//2)
print(5.0//2)
```

**输出:**

```
2
-3
2.0
```

对于非常大的数字，单除法运算符通常表现异常。考虑下面的例子。

**例 1:**

```
# single division
print(1000000002/2)

# Gives wrong output
print(int(((10 ** 17) + 2)/2))

# Gives Correct output
print(((10 ** 17) + 2)//2)
```

**输出:**

```
500000001.0
50000000000000000
50000000000000001

```

**例 2:**

```
x = 10000000000000000000006
if int(x / 2) == x // 2:
    print("Hello")
else:
    print("World")
```

**输出:**

```
World

```

如果单除法运算符表现正常，输出应该是 Hello，因为 2 正确地除了 x。但是输出是 World，因为单除法运算符和双除法运算符**之后的结果不一样**。

这一事实可用于程序，例如为一个大 n

```
n = 10000000000

s1 = int(n * (n + 1) / 2)
s2 = n * (n + 1) // 2

print("Sum using single division operator : ", s1)
print("Sum using double division operator : ", s2)
```

求前 n 个数的和

**输出:**

```
Sum using single division operator :  50000000005000003584
Sum using double division operator :  50000000005000000000

```

因此，使用单除法运算符得到的结果是错误的，而使用双除法运算符得到的结果是正确的。这是 Python 中双除法运算符相对于单除法运算符的巨大优势。