# 如何用 Python 做微积分？

> 原文:[https://www . geeksforgeeks . org/如何使用 python 进行演算/](https://www.geeksforgeeks.org/how-to-do-calculus-with-python/)

**微积分**是专注于极限、函数、导数、积分和无穷级数的数学分支。我们将使用[](https://www.sympy.org/en/index.html)**库用 python 做微积分。SymPy 是一个用于符号数学的 Python 库。它的目标是成为一个功能齐全的计算机代数系统(CAS)，同时保持代码尽可能简单，以便易于理解和扩展。SymPy 完全是用 Python 编写的。**

****安装:****

```
pip install sympy
```

**如果我们想写任何一个符号表达式，首先我们必须声明它的符号变量。为此，我们可以使用以下两个函数:**

*   ****症状。Symbol():** 用于通过将变量作为字符串传递到其参数中来声明单个变量。**
*   ****sympy.symbols():** 用于通过将变量作为字符串传递到其参数中来声明多变量。所有的变量必须用一个空格分隔，形成一个字符串。**

## **区别**

**我们可以使用 **diff(func，var)** 方法来区分任何一种症状表现。参数*函数*表示要微分的症状表达式，*变量*表示我们要微分的变量。**

****例 1:****

 **## 蟒 3

```
# Importing library
import sympy as sym

# Declaring variables
x, y, z = sym.symbols('x y z')

# expression of which we have to find derivative
exp = x**3 * y + y**3 + z

# Differentiating exp with respect to x
derivative1_x = sym.diff(exp, x)
print('derivative w.r.t x: ',
      derivative1_x)

# Differentiating exp with respect to y
derivative1_y = sym.diff(exp, y)
print('derivative w.r.t y: ',
      derivative1_y)
```** 

****输出:****

```
derivative w.r.t x:  3*x**2*y
derivative w.r.t y:  x**3 + 3*y**2
```

**我们也可以使用 **diff(func，var，n)** 方法找到更高的导数。这里，参数 *n* 表示待求的第 n 阶导数。**

****例 2:****

 **## 蟒 3

```
# Finding second derivative
# of exp with respect to x
derivative2_x = sym.diff(exp, x, 2)
print('second derivative w.r.t. x: ',
      derivative2_x)

# Finding second derivative
# of exp with respect to y
derivative2_y = sym.diff(exp, y, 2)
print('second derivative w.r.t. y: ',
      derivative2_y)
```** 

****输出:****

```
second derivative w.r.t. x:  6*x*y
second derivative w.r.t. y:  6*y
```

## **综合**

**可以通过 **integrate()** 函数对超越初等函数和特殊函数进行不定积分和定积分。**

> **不定积分语法:sympy . integral(func，var)
> 
> 定积分语法:sympy . integral(func，(var，lower_limit，upper_limit))**

**参数 *func* 表示待微分的症状表达式， *var* 表示我们要微分的变量，*下限*表示定积分的下限，*上限*表示定积分的上限。**

****注:** ∞在 SymPy 中为 oo。**

****例 1:****

 **## 蟒 3

```
# Indefinite integration of cos(x) w.r.t. dx
integral1 = sym.integrate(sym.cos(x), x)
print('indefinite integral of cos(x): ',
      integral1)

# definite integration of cos(x) w.r.t. dx between -1 to 1
integral2 = sym.integrate(sym.cos(x), (x, -1, 1))
print('definite integral of cos(x) between -1 to 1: ',
      integral2)

# definite integration of exp(-x) w.r.t. dx between 0 to ∞
integral3 = sym.integrate(sym.exp(-x), (x, 0, sym.oo))
print('definite integral of exp(-x) between 0 to ∞: ',
      integral3)
```** 

****输出:****

```
indefinite integral of cos(x):  sin(x)
definite integral of cos(x) between -1 to 1:  2*sin(1)
definite integral of exp(-x) between 0 to ∞:  1
```

## **限制**

**可以使用**极限(函数、变量、点)计算函数的极限。**所以，如果你想把 f(x)的极限计算为 x- > 0，你就要发出极限(f，x，0)。**

****示例:****

## **蟒蛇 3**

```
# Calculating limit of f(x) = x as x->∞
limit1 = sym.limit(x, x, sym.oo)
print(limit1)

# Calculating limit of f(x) = 1/x as x->∞
limit2 = sym.limit(1/x, x, sym.oo)
print(limit2)

# Calculating limit of f(x) = sin(x)/x as x->0
limit3 = sym.limit(sym.sin(x)/x, x, 0)
print(limit3)
```

****输出:****

```
oo
0
1
```

## **级数展开**

**我们也可以计算函数围绕一个点的泰勒级数展开式。要计算 f(x)围绕点 x=x <sub>0</sub> 的展开，根据顺序 x <sup>n</sup> ，使用 **sympy.series(f，x，x <sub>0</sub> ，n)** 。x <sub>0</sub> 和 n 可以省略，这种情况下将使用默认值 x <sub>0</sub> =0 和 n=6。**

****例:****

 **## 蟒 3

```
# assign series
series1 = sym.series(sym.cos(x), x)
print(series1)

# assign series
series2 = sym.series(1/sym.cos(x), x, 0, 4)
print(series2)
```** 

****输出:****

```
1 - x**2/2 + x**4/24 + O(x**6)
1 + x**2/2 + O(x**4)
```

**末尾的 O(x <sup>4</sup> )或 O(x <sup>6</sup> )项是指所有幂次大于或等于 x <sup>4</sup> 或 x <sup>6</sup> 的 x 项都被省略。**