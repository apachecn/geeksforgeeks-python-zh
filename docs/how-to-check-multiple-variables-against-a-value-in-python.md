# 如何在 Python 中对照一个值检查多个变量？

> 原文:[https://www . geesforgeks . org/如何对照 python 中的值检查多个变量/](https://www.geeksforgeeks.org/how-to-check-multiple-variables-against-a-value-in-python/)

给定一些变量，任务是编写一个 Python 程序来对照一个值检查多个变量。在 Python 中，有三种可能的已知方法可以实现这一点:

**方法#1:** 使用 or 运算符

这非常简单明了。下面的代码片段说明了这个方法。

**例 1:**

## 蟒蛇 3

```
# assigning variables
a = 100
b = 0
c = -1

# checking multiple variables against a value
if a == -1 or b == 100 or c == -1:
    print('Value Found!')
else:
    print('Not Found!')
```

**输出:**

```
Value Found!
```

**方法#2:** 在关键字中使用

它通常用于搜索序列，但可以很好地替换上面的代码。

## 蟒蛇 3

```
# assigning variables
a = 100
b = 0
c = -1

# checking multiple variables against a value
if a in [100, 0, -1]:
    print('Value Found!')
else:
    print('Not Found!')
```

**输出:**

```
Value Found!
```

您也可以将其用于反向语句:

**例 2:**

## 蟒蛇 3

```
# assigning variables
a = 90

# checking multiple variables against a value
if a not in [0, -1, 100]:
    print('Value Found!')
else:
    print('Not Found!')
```

**输出:**

```
Value Found!
```

**方法#2:** 使用==运算符

当用单个值检查时，这种方法仅适用于多个变量。

**例 1:**

## 蟒蛇 3

```
# assigning variables
a = 9
b = 9
c = 9

# checking multiple variables against a value
if a == b == c == 9:
    print('Value Found!')
else:
    print('Not Found!')
```

**输出:**

```
Value Found!
```