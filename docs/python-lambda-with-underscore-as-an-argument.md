# 以下划线为参数的 Python Lambda

> 原文:[https://www . geesforgeks . org/python-lambda-以下划线作为参数/](https://www.geeksforgeeks.org/python-lambda-with-underscore-as-an-argument/)

在 Python 中，我们使用 lambda 关键字来声明匿名函数。Lambda 函数的行为与使用' def '关键字声明的常规函数的行为相同。以下是 Python lambda 函数的一些特性:

*   A lambda function can accept multiple parameters, but they only contain one expression.
*   Lambda function for returning function objects.
*   Syntactically, lambda function is limited to one expression.

**注:**更多信息请参考 [Python lambda](https://www.geeksforgeeks.org/python-lambda/)

## 创建λ函数

可以使用`lambda`关键字创建 Lambda 函数。我们使用给定的语法来声明 lambda 函数:

```
lambda argument(s) : expression
```

**例:**

```
remainder = lambda num: num % 2

print(remainder(5))
```

**输出:**

```
1
```

## 带下划线的 Python Lambda

“_”是变量名。该变量名通常是被忽略变量的名称。

**例:**

```
l = lambda _: True

l(1)
```

**输出:**

```
True
```

当我们想要为每个输入获得特定的输出时，可以使用这个函数。