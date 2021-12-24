# 在 Python 中生成随机 Id

> 原文:[https://www.geeksforgeeks.org/generating-random-ids-python/](https://www.geeksforgeeks.org/generating-random-ids-python/)

在 python 中，有不同的方法来生成 id。让我们看看如何在不使用内置 python 库的情况下，使用 Python 生成不同类型的 Id。

#### **1。生成随机整数作为标识'**

**代码#1 :** 打印 10 个 1 到 100 之间的随机数值。

## 蟒蛇 3

```py
# Python3 code to demonstrate the
# random generation of Integer id's

import random

# determines how many values
# will be printed
for x in range(10):

    # print 10 random values
    # between 1 and 100
    print (random.randint(1, 101))
```

输出:

```py
76
72
7
78
77
19
24
23
77
96
```

**代码#2 :** 打印 1 到 100 之间的 5 的倍数的随机数。

## 蟒蛇 3

```py
# Python3 code to demonstrate
# the random generation of id's
# which are multiple of 5

import random

# determines how many
# values will be printed
for x in range(10):

    # print 10 random values between
    # 1 and 100 which are multiple of 5
    print (random.randint(1, 20) * 5)
```

输出:

```py
60
30
35
100
85
25
100
20
90
85
```

> **缺点:**
> 
> *   生成随机数不是唯一的，相同的数字可以重复。
> *   它只生成整数值。

#### **2。生成随机字符串作为标识'**

生成由字母和数字组成的随机字符串 id。这在生成密码时非常有用，因为它提供了加密和解密技术。

**代码#1 :** 展示如何生成随机字符串 id。

## 蟒蛇 3

```py
# Python3 code to demonstrate the
# random generation of string id's

import random
import string

# Generate a random string
# with 32 characters.
random = ''.join([random.choice(string.ascii_letters
            + string.digits) for n in range(32)])

# print the random
# string of length 32
print (random)
```

输出:

```py
Rf2IdqUNkURNN6mw82kSpyxQe9ib3usX
```

**代码#2 :** 使用函数调用

## 蟒蛇 3

```py
# Python3 code to demonstrate
# the random generation of string id's

import random
import string

# defining function for random
# string id with parameter
def ran_gen(size, chars=string.ascii_uppercase + string.digits):
    return ''.join(random.choice(chars) for x in range(size))

# function call for random string
# generation with size 8 and string
print (ran_gen(8, "AEIOSUMA23"))
```

输出:

```py
S2M2IEAO
```

[使用 Python 中的 UUID 生成随机 id](https://www.geeksforgeeks.org/generating-random-ids-using-uuid-python/)