# 强大的一行 Python 代码

> 原文:[https://www . geesforgeks . org/power-one-liner-python-codes/](https://www.geeksforgeeks.org/powerful-one-liner-python-codes/)

Python 是一种广泛使用的通用高级编程语言。Python 程序通常比 Java 等其他编程语言小。程序员必须键入相对较少的内容，语言的缩进要求使它们始终可读。但是，Python 程序可以使用一些单行代码变得更加简洁。这些可以节省时间，因为可以输入更少的代码。

> 参考下面的文章来了解更多关于 Python 的知识。
> 
> *   [Python 基础知识](https://www.geeksforgeeks.org/python-3-basics/)

## Python 中的一行程序

<font size="4">**一行#1:**</font> 在列表中输入空格分隔的整数:

假设您想从控制台获取空格分隔的输入，并将其转换为列表。为此，可以使用以`int()`方法和`input().split()`方法为参数的`[map()](https://www.geeksforgeeks.org/python-map-function/)`函数。这里`int()`方法用于将输入转换为`int`类型，`input().split()`方法用于从控制台获取输入并按空格分割输入。下面是实现。

```py
lis = list(map(int, input().split()))
```

**注意:**想了解更多 Python `map()`功能[点击这里](https://www.geeksforgeeks.org/python-map-function/)。

<font size="4">**单线#2:**</font> 输入二维矩阵(当条目按行排列时):

下面给出了输入二维矩阵时想到的最简单的方法。

```py
# Input for row and column
R = int(input()) 
C = int(input()) 

matrix = [] 

# for loop for row entries 
for i in range(R):          
    a =[] 

    # for loop for column entries 
    for j in range(C):
         a.append(int(input())) 
    matrix.append(a) 
```

上面的代码可以用一行代码编写，更加简洁，节省时间，特别是对于有竞争力的程序员来说。

```py
# Input for row and column
R = int(input())
C = int(input())

# Using list comprehension for input
matrix = [[int(input()) for x in range (C)] for y in range(R)] 
```

<font size="4">**One-Liner #3:**</font> 我们知道这个事实，但有时我们在翻译其他语言时往往会忽略它。这是两个数字的交换。最天真的做法是:

```py
temp = a
a = b
b = temp
```

然而，Python 也为此提供了一行代码。皮托尼克的方法是:

```py
# to swap two numbers a and b
a, b = b, a
```

<font size="4">**【One-Liner # 4】**</font>**【Lambda Functions(匿名函数)】**–Lambda Functions 是 python one liner functions，在要计算表达式时经常使用。

例如，假设我们想要创建一个函数，返回作为参数传递的数字的平方。正常的做法是:

```py
def sqr(x):
    return x * x

print(sqr(5))
```

**输出:**

```py
25

```

Lambda 函数在要计算单个表达式的地方替换一个函数。

```py
sqr = lambda x: x * x
print(sqr(5))
```

**输出:**

```py
25

```

<font size="4">**【One-Liner # 5】**</font>**列表理解**–这是创建列表的简洁方式。我们可以利用列表理解来代替通常的方法。

例如，我们想要创建一个直到 11 的偶数列表。正常的做法是:

```py
evenNumbers =[]
for x in range(11):
    if x % 2 == 0:
        evenNumbers.append(x)

print(evenNumbers)
```

**输出:**

```py
[0, 2, 4, 6, 8, 10]

```

蟒道:

```py
evenNumbers =[x for x in range(11) if x % 2 == 0]
print(evenNumbers)
```

**输出:**

```py
[0, 2, 4, 6, 8, 10]

```

<font size="4">**One-Liner #6:**</font> 使用 if-else 或 while 循环时，此技巧可能会有所帮助。与其这样做–

```py
if m == 1 or m == 2 or m == 3:
    pass
```

我们可以将其编码为:

```py
if m in [1, 2, 3]:
    pass
```

<font size="4">**One-Liner #7:**</font> 在 python 中有各种方法可以反转列表。
皮托尼克反转列表的方法:

*   **使用切片技术-** 该技术在反转时创建列表的副本。它会占用更多的内存。

```py
lis = [1, 2, 3]
reversed_list = lis[::-1]

print(reversed_list)
```

**输出:**

```py
[3, 2, 1]

```

*   使用反转功能-它可以就地反转列表对象的内容。

```py
lis = [1, 2, 3]
lis.reverse()

print(lis)
```

**输出:**

```py
[3, 2, 1]

```

<font size="4">**One-Liner #8:**</font> 你可以把这个当成挑战。制作单线 python 模式。

例如，将下面的代码精简为一行。

```py
for i in range(0, 5): 

        for j in range(0, i + 1): 
            # printing stars 
            print("* ", end ="") 

        # ending line after each row 
        print("\r")
```

**输出:**

```py
* 
* * 
* * * 
* * * * 
* * * * * 

```

把这一切浓缩在一行里很有趣。

```py
n = 5

# one liner code for half pyramid pattern
print('\n'.join('* ' * i for i in range(1, n + 1)))
```

**输出:**

```py
* 
* * 
* * * 
* * * * 
* * * * *

```

<font size="4">**单线#9**</font> 求阶乘。寻找阶乘的正常方法是迭代到那个数，并在每次迭代中乘以这个数。

```py
n = 5
fact = 1

for i in range(1, n + 1): 
    fact = fact * i 
print (fact) 
```

**输出:**

```py
120

```

我们可以使用`math.factorial(x)`–它返回 x 的阶乘。但是如果数字是负的或非整数，它会引起值错误。

```py
import math

n = 5
print(math.factorial(n))
```

**输出:**

```py
120

```

还有一种简洁地求阶乘的方法是使用`reduce()`和λ函数。

```py
import functools

n = 5
print(functools.reduce(lambda x, y: x * y, range(1, n + 1)))
```

**输出:**

```py
120

```

<font size="4">**【单线#10:**</font> 在一条线上查找集合的所有子集。
通常的方式需要大量的努力，在这里[可以看到](https://www.geeksforgeeks.org/power-set/)。使用`itertools.combinations()`可以用更简单的方式完成

```py
from itertools import combinations

# list of all subsets of 
# length r (r = 2 in this example) 
print(list(combinations([1, 2, 3, 4], 2)))
```

**Output:**

```py
[(1, 2), (1, 3), (1, 4), (2, 3), (2, 4), (3, 4)]

```

<font size="4">**【One-Liner # 11:**</font>读取 python 中的文件，并将其输入到列表中。

```py
file = open('gfg.txt', 'r') 
lis =[]

for each in file:

    # removing '\n' from the end of the string
    a = each[:-1] 
    lis.append(a)

file.close()
```

一个班轮代码是:

```py
lis = [line.strip() for line in open('gfg.txt', 'r')]
```