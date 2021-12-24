# Python 中的嵌套 Lambda 函数

> 原文:[https://www . geesforgeks . org/nested-lambda-function-in-python/](https://www.geeksforgeeks.org/nested-lambda-function-in-python/)

**先决条件:** [巨蟒λ](https://www.geeksforgeeks.org/python-lambda/)

在 Python 中，匿名函数意味着函数没有名称。正如我们已经知道的，def 关键字用于定义普通函数，lambda 关键字用于创建匿名函数。当我们在另一个 lambda 函数中使用 lambda 函数时，它被称为**嵌套 Lambda 函数**。

**例 1:**

```py
# Python program to demonstrate
# nested lambda functions

f = lambda a = 2, b = 3:lambda c: a+b+c

o = f()
print(o(4))
```

**输出:**

```py
9
```

这里，当调用参数为 4 的对象 o 时，控制转移到 f()，这是整个 lambda 函数的调用者对象。然后执行以下操作-

*   The nested lambda function of takes the values of A and B in the first lambda function as a=2 and b=3.
*   It gets the value of C from the caller object O, which passes c = 4.
*   The final output we get is the sum of A, B and C, which is 9.

**例 2:**

```py
# Python program to demonstrate
# nested lambda functions

square = lambda x: x**2
product = lambda f, n: lambda x: f(x)*n

ans = product(square, 2)(10)
print(ans)
```

**输出:**

```py
200
```

在上面的例子中，当乘积函数被调用时，平方函数被绑定到 f，2 被绑定到 n，然后 n 返回一个函数，该函数被绑定到乘积，当用 10 调用时，x 被赋值给这个函数，然后调用平方函数，它返回 100，这个函数又与 n 相乘，n 是 2。所以它最终会返回 200。