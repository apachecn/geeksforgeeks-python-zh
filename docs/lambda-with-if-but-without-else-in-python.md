# Python 中带 if 但不带 else 的 Lambda

> 原文:[https://www . geesforgeks . org/lambda-with-if-but-not-else-in-python/](https://www.geeksforgeeks.org/lambda-with-if-but-without-else-in-python/)

在 Python 中， [**Lambda 函数**](https://www.geeksforgeeks.org/python-lambda/) 是匿名函数，也就是说它是一个没有名字的函数。它可以有任意数量的参数，但只能有一个表达式，该表达式将被计算并返回。它必须有一个返回值。

由于 lambda 函数必须对每个有效输入都有一个返回值，我们不能用 *if* 来定义它，但不能用 *else* 来定义，因为我们没有指定如果 *if 条件*为假，即其 *else* 部分，我们将返回什么。

让我们用一个简单的例子来理解这一点，lambda 函数只在大于 0 时使用 *if* 对一个数进行平方，但不使用 *else* 。

**示例#1:**

## 蟒蛇 3

```py
# Lambda function with if but without else.
square = lambda x : x*x if(x > 0)

print(square(6))
```

**输出:**

```py
File "/home/2c8c59351e1635b6b026fb3c7fc17c8f.py", line 2
    square = lambda x : x*x if(x > 0)
                                    ^
SyntaxError: invalid syntax
```

上面的代码显示了语法错误，因为我们知道 lambda 函数必须返回值，如果 x > 0，这个函数返回 x*x，并且它没有指定如果 x 的值小于或等于 0，将返回什么。

为了纠正它，我们需要指定如果*if-条件*为假将返回什么，即我们必须指定它的*否则*部分。

让我们看看上面带有 *else* 部分的代码。

**代码:**

## 蟒蛇 3

```py
# Lambda function with if-else
square = lambda x : x*x if(x > 0) else None

print(square(4))
```

**输出:**

```py
16
```

**例 2:** 第一个代码是 *if* 但是没有 *else* ，那么第二个代码是 *if-else* 。

## 蟒蛇 3

```py
# Example of lambda function using if without else
mod = lambda x : x if(x >= 0)

print(mod(-1))
```

**输出:**

```py
File "/home/20b09bdd29e24dfe24c185cd99dfcdfa.py", line 2
    mod = lambda x : x if(x >= 0)
                                ^
SyntaxError: invalid syntax
```

现在，让我们看看它使用 if-else。

## 蟒蛇 3

```py
# Example of lambda function using if-else
mod = lambda x : x if(x >= 0) else -x

print(mod(-1))
```

**输出:**

```py
1
```

**示例#3:** 第一个代码有 if 但没有 else，然后第二个代码有 if-else。

## 蟒蛇 3

```py
# Example of lambda function using if without else
max = lambda a, b : x if(a > b)

print(max(1, 2))
```

**输出:**

```py
File "/home/8cf3856fc13d0ce75edfdd76793bdde4.py", line 2
    max = lambda a, b : x if(a > b)
                                  ^
SyntaxError: invalid syntax
```

现在，让我们看看它使用 if-else。

## 蟒蛇 3

```py
# Example of lambda function using if-else
max = lambda a, b : a if(a > b) else b

print(max(1, 2))
print(max(10, 2))
```

**输出:**

```py
2
10
```