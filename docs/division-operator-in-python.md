# Python 中的除法运算符

> 原文:[https://www.geeksforgeeks.org/division-operator-in-python/](https://www.geeksforgeeks.org/division-operator-in-python/)

考虑下面 Python 中的语句。

## 蟒蛇 3

```
# A Python program to demonstrate the use of
# "//" for integers
print (5//2)
print (-5//2)
```

**输出:**

```
2
-3
```

第一个输出很好，但是如果我们来到 Java/C++世界，第二个输出可能会感到惊讶。在 Python 中，“//”运算符充当整数和浮点参数的基底除法。但是，如果其中一个参数是浮点型的，则运算符/返回浮点值(这类似于 C++)

**注:**

“//”运算符用于返回小于或等于指定表达式或值的最接近的整数值。所以从上面的代码来看，5//2 返回 2。你知道 5/2 是 2.5，最近的小于等于的整数是 2[5//2]。(它与普通数学相反，在普通数学中值为 3)。

## 蟒蛇 3

```
# A Python program to demonstrate use of
# "/" for floating point numbers
print (5.0/2)
print (-5.0/2)
```

**输出:**

```
2.5
-2.5
```

**真正的楼层划分符是“//”。它返回整数和浮点参数的 floor 值。**

## 蟒蛇 3

```
# A Python program to demonstrate use of
# "//" for both integers and floating points
print (5//2)
print (-5//2)
print (5.0//2)
print (-5.0//2)
```

**输出:**

```
2
-3
2.0
-3.0
```

详见[本](https://ide.geeksforgeeks.org/Rm9JMm)举例。

本文由 **Arpit Agrawal** 供稿。如果你发现任何不正确的地方，请写评论，或者你想分享更多关于上面讨论的话题的信息