# Python 中的 divmod()及其应用

> 原文:[https://www.geeksforgeeks.org/divmod-python-application/](https://www.geeksforgeeks.org/divmod-python-application/)

python 中的 divmod()方法接受两个数字，并返回一对由它们的商和余数组成的数字。

**语法:**

```
divmod(x, y)
x and y : x is numerator and y is denominator
x and y must be non complex
```

**示例:**

```
Input : x = 9, y = 3
Output :(3, 0)

Input : x = 8, y = 3
Output :(2, 2)
```

**说明:**div mod()方法取两个参数 x 和 y，其中 x 作为分子，y 作为分母。该方法同时计算 **x // y** 和 **x % y** ，并返回两个值。

*   如果 x 和 y 是整数，返回值为

```
(x // y, x % y)
```

*   如果 x 或 y 是浮点数，结果是

```
(q, x % y), *where q is the whole part of the quotient.*
```

## 蟒蛇 3

```
# Python3 code to illustrate divmod()
# divmod() with int
print('(5, 4) = ', divmod(5, 4))
print('(10, 16) = ', divmod(10, 16))
print('(11, 11) = ', divmod(11, 11))
print('(15, 13) = ', divmod(15, 13))

# divmod() with int and Floats
print('(8.0, 3) = ', divmod(8.0, 3))
print('(3, 8.0) = ', divmod(3, 8.0))
print('(7.5, 2.5) = ', divmod(7.5, 2.5))
print('(2.6, 10.7) = ', divmod(2.6, 0.5))
```

**输出:**

```
(5, 4) =  (1, 1)
(10, 16) =  (0, 10)
(11, 11) =  (1, 0)
(15, 13) =  (1, 2)
(6.0, 5) =  (2.0, 2.0)
(3, 9.0) =  (0.0, 3.0)
(13.5, 6.2) =  (3.0, 0.0)
(1.6, 10.7) =  (5.0, 0.10000000000000009)
```

### **错误和异常**

1.  如果其中一个参数(比如 x 和 y)是浮点数，那么结果就是(q，x%y)。这里，q 是商的全部。
2.  如果第二个参数为 0，则返回*除零误差*
3.  如果第一个参数为 0，则返回(0，0)

**实际应用:**使用 divmod()函数检查一个数是否为素数。

**示例:**

```
Input : n = 7
Output :Prime

Input : n = 15
Output :Not Prime
```

**算法**

1.  初始化一个新的变量，比如 x，给定整数，变量计数器为 0
2.  运行一个循环，直到给定的整数变成 0，并继续递减。
3.  将 divmod(n，x)返回的值保存在两个变量中，比如 p 和 q
4.  检查 q 是否为 0，这将意味着 n 完全可以被 x 整除，从而增加计数器值
5.  检查计数器值是否大于 2，如果是，则该数不是质数，否则是质数

## PYTHON3

```
# Python code to find if a number is
# prime or not using divmod()

# Given integer
n = 15
x = n

# Initialising counter to 0
count = 0
while x != 0:
    p, q = divmod(n, x)
    x -= 1
    if q == 0:
        count += 1
if count > 2:
    print('Not Prime')
else:
    print('Prime')
```

**输出:**

```
Not Prime
```

**更多应用:**

**例 1:**

## 蟒蛇 3

```
# Sum of digits of a number using divmod
num = 86
sums = 0
while num != 0:
    use = divmod(num, 10)
    dig = use[1]
    sums = sums + dig
    num = use[0]
print(sums)
```

**输出:**

```
14
```

**例 2:**

## 蟒蛇 3

```
# reversing a number using divmod
num = 132
pal = 0
while num != 0:
    use = divmod(num, 10)
    dig = use[1]
    pal = pal*10+dig
    num = use[0]
print(pal)
```

**输出:**

```
231 
```