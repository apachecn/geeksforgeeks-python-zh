# 如何在 Python 中生成随机字母？

> 原文:[https://www . geesforgeks . org/如何生成 python 中的随机字母/](https://www.geeksforgeeks.org/how-to-generate-a-random-letter-in-python/)

在本文中，让我们讨论如何生成随机字母。Python 提供了丰富的模块支持，其中一些模块可以帮助我们生成随机数和字母。使用各种 Python 模块，我们有多种方法可以做到这一点。

**方法一:使用字符串和随机模块**

字符串模块有一个特殊的函数 ascii_letters，它返回一个包含 a-z 和 A-Z 中所有字母的字符串，即所有小写字母和大写字母。使用 [**random.choice()**](https://www.geeksforgeeks.org/python-numbers-choice-function/) 我们可以从该字符串中选择任何特定的字符。

**代码:**

## 蟒蛇 3

```py
# Import string and random module
import string
import random

# Randomly choose a letter from all the ascii_letters
randomLetter = random.choice(string.ascii_letters)
print(randomLetter)
```

**输出:**

```py
w
```

**方法二:使用** **只随机模块**

使用 [random.randint(x，y)](https://www.geeksforgeeks.org/python-randint-function/) 我们可以生成从 x 到 y 的随机整数，因此我们可以随机生成其中一个字母的 ASCII 值，然后使用 [chr()](https://www.geeksforgeeks.org/chr-in-python/) 函数将其类型转换为 char。

**代码:**

## 蟒蛇 3

```py
# Import string and random module
import random

# Randomly generate a ascii value
# from 'a' to 'z' and 'A' to 'Z'
randomLowerLetter = chr(random.randint(ord('a'), ord('z')))
randomUpperLetter = chr(random.randint(ord('A'), ord('Z')))
print(randomLowerLetter, randomUpperLetter)
```

**输出:**

```py
n M
```