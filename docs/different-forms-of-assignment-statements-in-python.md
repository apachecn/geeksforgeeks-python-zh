# Python 中不同形式的赋值语句

> 原文:[https://www . geesforgeks . org/不同形式的赋值语句-in-python/](https://www.geeksforgeeks.org/different-forms-of-assignment-statements-in-python/)

我们使用 **Python 赋值语句**将对象赋给名称。赋值语句的目标写在等号(=)的左边，右边的对象可以是计算对象的任意表达式。

Python 中赋值有一些重要的属性:-

*   赋值创建对象引用，而不是复制对象。
*   当第一次给变量赋值时，Python 会创建一个变量名。
*   引用名称之前必须先分配名称。
*   有些操作会隐式执行赋值。

**分配报表:-**

**1。基本形式:**

这种形式是最常见的形式。

```py
student = 'Geeks'
print(student)
```

**输出**

```py
Geeks
```

**2。元组分配:**

```py
# equivalent to: (x, y) = (50, 100)
x, y = 50, 100  

print('x = ', x)
print('y = ', y)
```

**输出**

```py
x = 50 
y = 100

```

当我们在=的左侧编码元组时，Python 通过位置将右侧的对象与左侧的目标配对，并从左到右分配它们。因此，x 和 y 的值分别是 50 和 100。

**3。列表分配:**

这与元组赋值的工作方式相同。

```py
[x, y] = [2, 4]

print('x = ', x)
print('y = ', y)
```

**输出**

```py
x = 2
y = 4

```

**4。序列分配:**

在 Python 的最新版本中，元组和列表赋值已经被推广到我们现在称之为序列赋值的实例中——任何名称序列都可以被赋值给任何值序列，Python 通过位置一次赋值一个项目。

```py
a, b, c = 'HEY'

print('a = ', a)
print('b = ', b)
print('c = ', c)
```

**输出**

```py
a = H
b = E
c = Y

```

**5。扩展序列拆包:**

它允许我们更灵活地选择要分配的序列部分。

```py
p, *q = 'Hello'

print('p = ', p)
print('q = ', q)
```

这里，p 与右边字符串中的第一个字符匹配，q 与其余字符匹配。给带星号的名称(*q)分配一个列表，该列表收集序列中未分配给其他名称的所有项目。

**输出**

```py
p = H
q = ['e', 'l', 'l', 'o']

```

这对于常见的编码模式来说尤其方便，例如拆分一个序列并访问它的前部和其余部分。

```py
ranks = ['A', 'B', 'C', 'D']
first, *rest = ranks

print("Winner: ", first)
print("Runner ups: ", ', '.join(rest))
```

**输出**

```py
Winner: A
Runner ups: B, C, D

```

**6。多目标分配:**

```py
x = y = 75

print(x, y)
```

在这种形式中，Python 将对同一对象(最右边的对象)的引用分配给左边的所有目标。

**输出**

```py
75 75

```

**7。增强分配:**

增广赋值是一种将表达式和赋值相结合的速记赋值。

```py
x = 2

# equivalent to: x = x + 1
x += 1  

print(x)
```

**输出**

```py
3

```

还有其他几种扩充赋值形式:

```py
-=, **=, &=, etc.
```