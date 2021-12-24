# 如何用 Python 找到函数的梯度？

> 原文:[https://www . geesforgeks . org/如何使用 python 查找函数梯度/](https://www.geeksforgeeks.org/how-to-find-gradient-of-a-function-using-python/)

函数的梯度仅仅意味着函数的变化率。我们将使用 **numdifftools** 来寻找函数的梯度。

**示例:**

```py
Input : x^4+x+1
Output :Gradient of x^4+x+1 at x=1 is  4.99

Input :(1-x)^2+(y-x^2)^2
Output :Gradient of (1-x^2)+(y-x^2)^2 at (1, 2) is  [-4\.  2.] 

```

**进场:**

*   **对于单变量函数:**对于单变量函数，我们可以直接使用“λ”进行定义，如下所示:-

    ```py
    g=lambda x:(x**4)+x+1
    ```

*   **For Multi-Variable Function:** We will define a function using “def” and pass an array “x” and it will return multivariate function as described below:-

    ```py
    def rosen(x): 
        return (1-x[0])**2 +(x[1]-x[0]**2)**2
    ```

    其中“rosen”是函数名,“x”作为数组传递。`x[0]`和`x[1]`是与数组中定义的顺序相同的数组元素，即上面定义的函数是`(1-x^2)+(y-x^2)^2`。

同样，我们也可以用上述同样的方式定义多于两个变量的函数。

**使用的方法:**渐变()
T3】语法:

```py
nd.Gradient(func_name)
```

**示例:**

```py
import numdifftools as nd

g = lambda x:(x**4)+x + 1
grad1 = nd.Gradient(g)([1])
print("Gradient of x ^ 4 + x+1 at x = 1 is ", grad1)

def rosen(x): 
    return (1-x[0])**2 +(x[1]-x[0]**2)**2

grad2 = nd.Gradient(rosen)([1, 2])
print("Gradient of (1-x ^ 2)+(y-x ^ 2)^2 at (1, 2) is ", grad2)
```

**输出:**

```py
Gradient of x^4+x+1 at x=1 is  4.999999999999998
Gradient of (1-x^2)+(y-x^2)^2 at (1, 2) is  [-4\.  2.]
```