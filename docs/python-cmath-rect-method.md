# Python–cmath . rect()方法

> 原文:[https://www.geeksforgeeks.org/python-cmath-rect-method/](https://www.geeksforgeeks.org/python-cmath-rect-method/)

**cmath** 是 Python 内置模块，用于复数数学。cmath 模块有一个方法 rect()，用于将极坐标转换为矩形形式。

> **语法:** cmath.rect(r，phi)
> 
> **参数:**需要两个参数。第一个参数 r 表示复数的模，第二个参数表示相位。这两个参数都是必需的。无是可选的。
> 
> **Return:** 返回一个复数 Z，其模为 r，相位为φ。

**注:**r *(math . cos(φ)+math . sin(φ)* 1j)与此方法等价。

**例 1:**

## 蟒蛇 3

```
# Import the Library
import cmath 

# Printing the result
print (cmath.rect(3,10))
```

**输出:**

```
(-2.517214587229357-1.6320633326681093j)

```

**实施例 2:** 在该实施例中，模数取为零。

## 蟒蛇 3

```
# Import the Library
import cmath 

# Printing the result
print (cmath.rect(0,1))
```

**输出:**

```
0j

```

**示例 3:** 在该示例中，相位被视为零

## 蟒蛇 3

```
# Import the Library
import cmath 

# Printing the result
print (cmath.rect(1,0))
```

**输出:**

```
(1+0j)

```