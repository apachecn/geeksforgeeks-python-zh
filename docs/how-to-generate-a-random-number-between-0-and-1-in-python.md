# 如何在 Python 中生成 0 到 1 之间的随机数？

> 原文:[https://www . geesforgeks . org/如何在 python 中生成介于 0 和 1 之间的随机数/](https://www.geeksforgeeks.org/how-to-generate-a-random-number-between-0-and-1-in-python/)

随机性的使用是现代算法配置和评估的重要部分。

在这里，我们将看到生成 0 和 1 之间的随机数的各种方法。

**方法 1:**

这里，我们将使用 [uniform()](https://www.geeksforgeeks.org/python-number-uniform-method/) 方法，该方法返回两个指定数字(都包括在内)之间的随机数。

**代码:**

## 蟒蛇 3

```
import random

print(random.uniform(0, 1))
```

**输出:**

```
0.0023922878433915162
```

**方法二:**

这里，我们将使用 random()方法，该方法返回一个介于 0 和 1 之间的随机浮点数。

**代码:**

## 蟒蛇 3

```
import random

print(random.random())
```

**输出:**

```
0.7769332461684861
```

**方法 3:**

这里，我们将使用 [numpy](https://www.geeksforgeeks.org/numpy-in-python-set-1-introduction/) 来生成随机数数组。

**代码:**

## 蟒蛇 3

```
import numpy as np

x=np.random.random(1)[0]
print(x)
```

**输出:**

```
0.03394418147881839
```

**方法 4:**

在这里，我们将看到生成随机数的自定义方法。

[randint()](https://www.geeksforgeeks.org/python-randint-function/) 是返回两个指定值之间的随机整数的方法。

**代码:**

## 蟒蛇 3

```
import random

print(random.randint(0, 10**5)/ 10**5)
```

**输出:**

```
0.59882
```