# Python 中的分数模块

> 原文:[https://www.geeksforgeeks.org/fraction-module-python/](https://www.geeksforgeeks.org/fraction-module-python/)

该模块支持有理数运算。它允许从整数、浮点数、数字、小数和字符串创建一个 Fraction 实例。

**分数实例:**分数实例可以由一对整数、另一个有理数或字符串构成。分数实例是可散列的，应该被视为不可变的。

1.  **class fractions.Fraction(numerator=0, denominator=1) :** This requires that numerator and denominator are instances of **numbers. Rational** and a fraction instance with value = (numerator/denominator) is returned. A zerodivision error is raised if denominator = 0.

    ```
    from fractions import Fraction

    print (Fraction(11, 35))
    # returns Fraction(11, 35)

    print (Fraction(10, 18))
    # returns Fraction(5, 9)

    print (Fraction())
    # returns Fraction(0, 1)
    ```

    **输出:**

    ```
    11/35
    5/9
    0

    ```

2.  **类分数。分数(其他分数):**这要求其他分数是**数的实例。Rational** 并返回一个具有相同值的分数实例。
3.  **class fractions.Fraction(float) :** This requires the **float** instance and a fraction instance with same value is returned.

    ```
    from fractions import Fraction

    print (Fraction(1.13))
    # returns Fraction(1272266894732165, 1125899906842624)
    ```

    **输出:**

    ```
    1272266894732165/1125899906842624

    ```

4.  **class fractions.Fraction(decimal) :** This requires the **decimal** instance and a fraction instance with same value is returned.

    ```
    from fractions import Fraction

    print (Fraction('1.13'))
    # returns Fraction(113, 100)
    ```

    **输出:**

    ```
    113/100

    ```

5.  **class fractions.Fraction(string) :** This requires the **string or unicode** instance instance and a fraction instance with same value is returned.

    **此实例的形式:**【符号】分子['/'分母]
    这里，符号表示'+'或'-'，分子和分母是一位数的字符串。

    ```
    from fractions import Fraction

    print (Fraction('8/25'))
    # returns Fraction(8, 25)

    print (Fraction('1.13'))
    # returns Fraction(113, 100)

    print (Fraction('3/7'))
    # returns Fraction(3, 7)

    print (Fraction('1.414213 \t\n'))
    # returns Fraction(1414213, 1000000)
    ```

    **输出:**

    ```
    8/25
    113/100
    3/7
    1414213/1000000

    ```

6.  **limit_denominator(max_denominator=1000000) :**
    *   这种方法对于找到给定浮点数的有理逼近很有用。
    *   该模块查找并返回最接近自身的分数，该分数的分母最多为 max _ 分母。
    *   该模块还可以通过使用**分子**属性返回最低项中给定分数的分子，通过使用**分母**属性返回分母。

    ```
    from fractions import Fraction

    print (Fraction('3.14159265358979323846'))
    # returns Fraction(157079632679489661923, 50000000000000000000)

    print (Fraction('3.14159265358979323846').limit_denominator(10000))
    # returns Fraction(355, 113)

    print (Fraction('3.14159265358979323846').limit_denominator(100))
    # returns Fraction(311, 99)

    print (Fraction('3.14159265358979323846').limit_denominator(10))
    # returns Fraction(22, 7)

    print (Fraction(125, 50).numerator)
    # returns 5

    print (Fraction(125, 50).denominator)
    # returns 2
    ```

    **输出:**

    ```
    157079632679489661923/50000000000000000000
    355/113
    311/99
    22/7
    5
    2

    ```

**对分数进行数学运算**

```
from fractions import Fraction

print (Fraction(113, 100) + Fraction(25, 18))
# returns Fraction(2267, 900)

print (Fraction(18, 5) / Fraction(18, 10))
# returns Fraction(2, 1)

print (Fraction(18, 5) * Fraction(16, 19))
# returns Fraction(288, 95)

print (Fraction(18, 5) * Fraction(15, 36))
# returns Fraction(3, 2)

print (Fraction(12, 5) ** Fraction(12, 10))
# returns 2.8592589556010197
```

**输出:**

```
2267/900
2
288/95
3/2
2.8592589556

```

**使用数学模块的各种功能进行基于分数的计算**

```
import math
from fractions import Fraction

print (math.sqrt(Fraction(25, 4)))
# returns 2.5

print (math.sqrt(Fraction(28,3)))
# returns 3.0550504633038935

print (math.floor(Fraction(3558, 1213)))
# returns 2

print (Fraction(math.sin(math.pi/3)))
# returns Fraction(3900231685776981, 4503599627370496)

print (Fraction(math.sin(math.pi/3)).limit_denominator(10))
# returns Fraction(6, 7)
```

**输出:**

```
2.5
3.0550504633
2.0
3900231685776981/4503599627370496
6/7

```

本文由**阿迪提·古普塔**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。