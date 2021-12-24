# Python 中链接比较运算符

> 原文:[https://www . geesforgeks . org/chaining-comparison-operators-python/](https://www.geeksforgeeks.org/chaining-comparison-operators-python/)

在编程语言中，检查两个以上的条件是非常常见的。假设我们要检查以下条件:

```
a < b < c

```

最常见的语法如下:

```
if a < b and b < c :
   {...}

```

在 Python 中，有一种更好的方法可以使用**比较运算符 Chaining** 来写这个。运算符的链接可以写成如下形式:

```
if a < b < c :
    {.....}

```

根据 Python 中的[结合律和优先级](https://www.geeksforgeeks.org/c-operator-precedence-associativity/)，Python 中所有的比较运算都具有相同的优先级，低于任何算术、移位或按位运算。同样与 C 不同的是，像 a < b < c 这样的表达式有着数学中惯用的解释。

Python 中的比较运算符列表:

```
">" | "<" | "==" | ">=" | "<=" | "!=" | "is" ["not"] | ["not"] "in"

```

**比较运算符中的链接:**

1.  比较产生布尔值:真或假。
2.  Comparisons can be chained arbitrarily. For example:

    ```
    x < y <= z is equivalent to x < y and y <= z, 
    ```

    除了 y 只计算一次。
    (但在这两种情况下，当发现 x < y 为假时，z 根本不被评估)。

3.  形式上，如果 a，b，c，…，y，z 是表达式，op1，op2，…，opN 是比较运算符，那么 a op1 b op2 c … y opN z 相当于 a op1 b 和 b op2 c 和… y opN z，只是每个表达式最多求值一次。
4.  Also,

    ```
    a op1 b op2 c 
    ```

    并不意味着 a 和 c 之间有任何比较，所以

    ```
     a < b > c
    ```

    是完全合法的。

```
# Python code to illustrate
# chaining comparison operators
x = 5
print(1 < x < 10)
print(10 < x < 20 )
print(x < 10 < x*10 < 100)
print(10 > x <= 9)
print(5 == x > 4)
```

输出:

```
True
False
True
True
True

```

**另一个例子:**

```
# Python code to illustrate
# chaining comparison operators
a, b, c, d, e, f = 0, 5, 12, 0, 15, 15
exp1 = a <= b < c > d is not e is f
exp2 = a is d > f is not c
print(exp1)
print(exp2)
```

输出:

```
True
False

```

**参考** : [Python 3 文档](https://docs.python.org/3/reference/expressions.html)

本文由 [**普拉蒂克·查哈尔**](https://www.linkedin.com/in/pratik-chhajer-4a102213b/) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。