# Python 中的布尔数据类型

> 原文:[https://www.geeksforgeeks.org/boolean-data-type-in-python/](https://www.geeksforgeeks.org/boolean-data-type-in-python/)

**Python** **布尔**类型是 Python 提供的内置数据类型之一，代表真或假两个值之一。一般用于表示表达式的真值。例如，1== 0 为真，而 2 < 1 为假。

## Python 布尔类型

布尔值只能有两种类型，即“真”或“假”。输出 ***<类>*** 指示变量是布尔数据类型。

### 示例:布尔类型

## 蟒蛇 3

```py
a = True
type(a)

b = False
type(b)
```

**输出:**

```py
<class 'bool'>
<class 'bool'>
```

## 评估变量和表达式

我们可以使用 **Python bool()** 函数来评估值和变量。此方法用于使用标准的真值测试过程将值返回或转换为布尔值，即真或假。

**语法:**

```py
bool([x])
```

### 示例:Python bool()方法

## 蟒蛇 3

```py
# Python program to illustrate
# built-in method bool()

# Returns False as x is not equal to y
x = 5
y = 10
print(bool(x==y))

# Returns False as x is None
x = None
print(bool(x))

# Returns False as x is an empty sequence
x = ()
print(bool(x))

# Returns False as x is an empty mapping
x = {}
print(bool(x))

# Returns False as x is 0
x = 0.0
print(bool(x))

# Returns True as x is a non empty string
x = 'GeeksforGeeks'
print(bool(x))
```

**Output**

```py
False
False
False
False
False
True
```

我们也可以在不使用 bool()函数的情况下计算表达式。布尔值将作为某种比较的结果返回。在下面的例子中，变量 res 将在相等比较发生后存储布尔值 False。

### 示例:表达式中的布尔值

## 蟒蛇 3

```py
# Declaring variables
a = 10
b = 20

# Comparing variables
print(a == b)
```

**输出:**

```py
False
```

## **整数和浮点数作为布尔值**

通过使用 Python 内置的 ***bool()*** 方法，可以将数字用作 bool 值。任何以零为值的整数、浮点数或复数都被认为是假的，而如果它们以任何正数或负数为值，则被认为是真的。

## 蟒 3

```py
var1 = 0
print(bool(var1))

var2 = 1
print(bool(var2))

var3 = -9.7
print(bool(var3))
```

**输出:**

```py
False
True
True
```

## **布尔运算符**

布尔运算是真值和假值的简单算术。这些值可以通过使用布尔运算符进行操作，这些运算符包括**、“或”和“非”**。常见的布尔运算有–

*   或者
*   和
*   不
*   ==(等效)
*   ！=(不等同)

### 布尔或运算符

如果任何一个输入为真，布尔或运算符返回真，否则返回假。

<figure class="table">假T22 真T30 假 T33】

| A | B | a 或 B |
| --- | --- | --- |
| 真 | 真 | 真 |
| 真 | 假 | 真 |
| 假 | 真 |
| 假 | 假 |

</figure>

### 示例:Python 布尔或运算符

## 蟒蛇 3

```py
# Python program to demonstrate
# or operator

a = 1
b = 2
c = 4

if a > b or b < c:
    print(True)
else:
    print(False)

if a or b or c:
    print("Atleast one number has boolean value as True")
```

**Output**

```py
True
Atleast one number has boolean value as True
```

在上面的例子中，我们使用了 Python boolean 和 if 语句以及 OR 运算符来检查 a 是否大于 b 或者 b 是否小于 c，如果任何条件为真(上面例子中的 b

### 布尔与运算符

如果任何一个输入为假，布尔 and 运算符返回假，否则返回真。

<figure class="table">假假T22 假T30 假 T32

| A | B | 甲乙 |
| --- | --- | --- |
| 真 | 真 | 真 |
| 真 | 假 | 假 |
| 假 | 真 |
| 假 | 假 |

</figure>

### 示例:Python 布尔与运算符

## 蟒蛇 3

```py
# Python program to demonstrate
# and operator

a = 0
b = 2
c = 4

if a > b and b<c:
    print(True)
else:
    print(False)

if a and b and c:
    print("All the numbers has boolean value as True")
else:
    print("Atleast one number has boolean value as False")
```

**Output**

```py
False
Atleast one number has boolean value as False
```

### 布尔非运算符

布尔非运算符只需要一个参数，并返回该参数的负数，即返回真表示假，返回假表示真。

<figure class="table">假T13】

| A | 不是 A |
| --- | --- |
| 真 | 假 |
| 真 | 真 |

</figure>

### 示例:Python 布尔非运算符

## 蟒蛇 3

```py
# Python program to demonstrate
# not operator

a = 0

if not a:
    print("Boolean value of a is False")
```

**Output**

```py
Boolean value of a is False
```

### 布尔==(等价)和！=(不等同)运算符

这两个运算符都用来表示两个结果。==(如果两个结果相等，等效运算符返回 True！=(如果两个结果不相同，非等价运算符返回 True。

### 示例:Python 布尔==(等效)和！=(不等同)运算符

## 蟒蛇 3

```py
# Python program to demonstrate
# equivalent an not equivalent
# operator

a = 0
b = 1

if a == 0:
    print(True)

if a == b:
    print(True)

if a != b:
    print(True)
```

**Output**

```py
True
True
```

### 操作员是

[是关键字](https://www.geeksforgeeks.org/is-keyword-in-python/)用来测试两个变量是否属于同一个对象。如果两个对象相同，测试将返回真，否则即使两个对象 100%相等，测试也将返回假。

### 示例:Python 是运算符

## 蟒蛇 3

```py
# Python program to demonstrate
# is keyword

x = 10
y = 10

if x is y:
    print(True)
else:
    print(False)

x = ["a", "b", "c", "d"]
y = ["a", "b", "c", "d"]

print(x is y)
```

**Output**

```py
True
False
```

### 操作员输入

运算符中的[检查成员资格，即检查值是否存在于列表、元组、范围、字符串等中。](https://www.geeksforgeeks.org/python-in-keyword/)

### 示例:在运算符中

## 蟒蛇 3

```py
# Python program to demonstrate
# in keyword

# Create a lits
animals = ["dog", "lion", "cat"]

# Check if lion in list or not
if "lion" in animals:
    print(True)
```

**Output**

```py
True
```