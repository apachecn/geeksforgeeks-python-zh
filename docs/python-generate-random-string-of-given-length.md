# Python |生成给定长度的随机字符串

> 原文:[https://www . geesforgeks . org/python-generate-random-string-of-length/](https://www.geeksforgeeks.org/python-generate-random-string-of-given-length/)

生成随机数的问题很常见，但有时，我们的应用程序要求我们更好地做到这一点，并为密码等应用程序提供一些生成随机数字和字母字符串的功能。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`random.choices()`**

随机模块的这一功能可以帮助我们实现这一任务，并为这一特定任务可能需要的整个循环提供一个线性替代。适用于 Python > v3.6。

```
# Python3 code to demonstrate
# generating random strings 
# using random.choices()
import string
import random

# initializing size of string 
N = 7

# using random.choices()
# generating random strings 
res = ''.join(random.choices(string.ascii_uppercase +
                             string.digits, k = N))

# print result
print("The generated random string : " + str(res))
```

**Output :**

```
The generated random string : 0D5YE91

```

**方法 2:使用`secrets.choice()`**

对于密码上更安全的随机数，可以使用秘密模块的这个功能，因为它的内部算法是以生成不太可预测的随机数的方式构建的。适用于 Python > v3.6。

```
# Python3 code to demonstrate
# generating random strings 
# using secrets.choice()
import secrets
import string

# initializing size of string 
N = 7

# using random.choices()
# generating random strings 
res = ''.join(secrets.choice(string.ascii_uppercase + string.digits)
                                                  for i in range(N))

# print result
print("The generated random string : " + str(res))
```

**Output :**

```
The generated random string : T7HPKVR

```