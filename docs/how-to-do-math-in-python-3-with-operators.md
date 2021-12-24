# 如何用运算符在 Python 3 中做数学？

> 原文:[https://www . geesforgeks . org/how-to-do-in-math-3-with-operators/](https://www.geeksforgeeks.org/how-to-do-math-in-python-3-with-operators/)

Python3 为我们提供了像整型和浮点型这样的数据类型，以及各种运算符来执行数学计算，用于图形绘制、机器学习算法、统计和数据分析。运算符是执行特定操作的符号，如果经常处理数字，这非常有用。运算符优先级指定当表达式中两个或多个具有不同优先级的运算符相邻时，运算符的求值顺序。下面是一元运算符和算术运算符的快速参考表。

## Python 中的运算符

<figure class="table">

| 类型 | 操作员 | 名字 | 例子 | 描述 |
| --- | --- | --- | --- | --- |
| 泌尿操作员 | – | 负的 | –x | 否定数值参数 |
|   | + | 加 | + x | 数值参数不变。 |
|   | ~ | 转化的 | –(x+1) | x 的逐位反转 |
| 算术运算符 | + | 添加 | x + y | 使用中间的“+”运算符添加两个操作数 |
|   | – | 减法 | x y | 使用中间的“-”运算符减去两个操作数 |
|   | * | 增加 | x * y | 在两个操作数之间使用“*”运算符相乘 |
|   | / | 分开 | x / y | 使用“/”运算符将左操作数与右操作数相除 |
|   | // | 楼层划分 | x // y | 使用“//”运算符将左操作数与右操作数相除并提供唯一的商作为输出

 |
|   | ** | 幂运算 | x ** y | x 的幂(幂)到 y 的幂 |
|   | % | 以…为模 | x % y | 使用“%”运算符将左操作数与右操作数相除并提供唯一的余数作为输出 |

</figure>

## 运算符优先级

<figure class="table">

| 操作员 | 意义 | 结合性 |
| --- | --- | --- |
| ** | 指数 | 从右向左 |
| ~x | 按位非(反转) | 左右 |
| +x，-x | 一元正，一元负 | 左右 |
| *, /, //, % | 乘法、除法、地板除法、模数 | 左右 |
| +, – | 加法，减法 | 左右 |

</figure>

**示例 1:** 一元运算符。

## 蟒蛇 3

```py
a = 2.202
b = -2.202

# This inverts the sign
# for both integer as
# well as float type
c = -a
print("Minus operator value 1:", c)
c = -b
print("Minus operator value 2:", c)

# This does not inverts the sign
# for both integer as well
# as float type
c = +a
print("Plus operator value 1:", c)
c = +b
print("Plus operator value 2:", c)

a = 2
b = -2

# This inverts the sign only
# for integer type as perform
# operation as per this '-(x + 1)'.
c = ~a  # -(2 + 1)
print("Invert operator value 1:", c)
c = ~b     # -(-2 + 1)
print("Invert operator value 2:", c)
```

**输出:**

```py
Minus operator value 1: -2.202
Minus operator value 2: 2.202
Plus operator value 1: 2.202
Plus operator value 2: -2.202
Invert operator value 1: -3
Invert operator value 2: 1
```

**例 2:** 加法运算符。

## 蟒蛇 3

```py
a = 4
b = -5

# This + operator performs
# addition of two operands
# or numbers
d = a + b
print("Addition value 1:", d)

a = [1, 2, 3, 4, 5]
b = [6, 7, 8, 9, 10]
d = []
for j in range(len(a)):
    d.append(a[j] + b[j])

print("Addition value 2:", d)
```

**输出:**

```py
Addition value 1: -1
Addition value 2: [7, 9, 11, 13, 15]
```

**例 3:** 减法运算符。

## 蟒蛇 3

```py
a = 4
b = -5

# This - operator performs
# subtraction of two operands
# or numbers
d = a - b
print("Subtraction value 1:",d)

a = [ 1 ,4,5]
b = [1, 2, 3]
print("Subtraction values:")
for i in range(len(a)) :
  print(a[i] - b[i])
```

**输出:**

```py
Subtraction value 1: 9
Subtraction values:
0
2
2
```

**例 4:** 乘法运算符。

## 蟒蛇 3

```py
a = 4
b = -5
c = 5.02

# This * operator performs
# Multiplication of two
# operands or numbers
d = a * b
print("Multiplication value 1:", d)

d = a * c
print("Multiplication value 2:", d)
```

**Output**

```py
Multiplication value 1: -20
Multiplication value 2: 20.08
```

**例 5:** 除法运算符。

## 蟒蛇 3

```py
a = 20
b = -5
c = 5.02

# This '/' operator performs
# Division of two operands
# or numbers
d = a / b
print("Division value 1:", d)

d = a / c
print("Division value 2:", d)
```

**输出:**

```py
Division value 1: -4.0
Division value 2: 3.9840637450199208
```

**例 6:** 楼层划分操作员。

## 蟒蛇 3

```py
a = 20
b = -5
c = 5.02

# This // operator performs
# Floor Division of two
# operands or numbers
d = a // b
print("Floor Division value 1:", d)

d = a // c
print("Floor Division value 2:", d)
```

**输出:**

```py
Floor Division value 1: -4
Floor Division value 2: 3.0
```

**例 7:** 指数算子。

## 蟒蛇 3

```py
a = 5
b = 3
c = -3

# This ** operator performs
# Exponential operation of two
# operands or numbers
d = a ** b
print("Exponent value 1:", d)

d = a ** c
print("Exponent value 2:", d)
```

**输出:**

```py
Exponent value 1: 125
Exponent value 2: 0.008
```

**例 8:** 模运算符。

## 蟒蛇 3

```py
a = 12 
b = 5
c = 3

# This % operator performs Modulous
# of two operands or numbers and
# return the remainder
d = a % b  
print("Modulous value 1:", d)

d = c % b
print("Modulous value 2:", d)
```

**输出:**

```py
Modulous value 1: 2
Modulous value 2: 3
```