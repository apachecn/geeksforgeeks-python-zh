# 如何在 Python 中使用 while True

> 原文:[https://www . geesforgeks . org/如何在 python 中真实使用/](https://www.geeksforgeeks.org/how-to-use-while-true-in-python/)

在本文中，我们将讨论如何在 Python 中使用 while True。

[**【While 循环】**](https://www.geeksforgeeks.org/python-while-loop/) 用于重复执行一个代码块，直到给定的布尔条件评估为假。如果我们写为真，那么循环将永远运行。

### 示例:当循环为真时

## 蟒蛇 3

```
# Python program to demonstrate
# while loop with True

while True:
    pass
```

如果我们运行上面的代码，那么这个循环将运行无限多次。为了摆脱这个循环，我们将明确使用 [break 语句](https://www.geeksforgeeks.org/python-break-statement/)。

让我们考虑下面的例子，我们想要找到前 N 个数字的和。让我们看看下面的代码，以便更好地理解。

### 示例:当使用 True 循环查找前 N 个数字的和时

## 蟒蛇 3

```
# Python program to demonstrate
# while loop with True

N = 10
Sum = 0

# This loop will run forever
while True:
    Sum += N
    N -= 1

    # the below condition will tell
    # the loop to stop
    if N == 0:
        break

print(f"Sum of First 10 Numbers is {Sum}")
```

**Output**

```
Sum of First 10 Numbers is 55
```

在上面的例子中，我们使用了 while True 语句来运行 while 循环，并且我们添加了一个 if 语句，当 N 的值变为 0 时，该语句将停止循环的执行。如果我们不写这个 If 语句，那么循环将永远运行，并且将开始将 N 的负值加到总和中。