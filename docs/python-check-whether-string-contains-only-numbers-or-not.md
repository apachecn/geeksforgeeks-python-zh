# Python |检查字符串是否只包含数字

> 原文:[https://www . geesforgeks . org/python-check-string-only-contains-numbers-or-not/](https://www.geeksforgeeks.org/python-check-whether-string-contains-only-numbers-or-not/)

给定一个字符串，编写一个 Python 程序来查找一个字符串是否只包含数字。让我们看看解决上述任务的几种方法。
**方法#1:使用 isdigit()方法**

## 蟒蛇 3

```
# Python3 code to demonstrate
# how to check whether string contains
# only numbers or not

# Initialising string
ini_string1 = '1234556'
ini_string2 = 'ab123bc'

# printing initial string
print ("Initial Strings : ", ini_string1, ini_string2)

# Using isdigit()
if ini_string1.isdigit():
    print ("String1 contains all numbers")
else:
    print ("String1 doesn't contains all numbers")

if ini_string2.isdigit():
    print ("String2 contains all numbers")
else:
    print ("String2 doesn't contains all numbers")
```

**Output:** 

```
Initial Strings :  1234556 ab123bc
String1 contains all numbers
String2 doesn't contains all numbers
```

**方法 2:使用正则表达式**

## 蟒蛇 3

```
# Python3 code to demonstrate
# how to check whether string contains
# only numbers or not
import re

# Initialising string
ini_string1 = '1234556'
ini_string2 = 'ab123bc'

# printing initial string
print ("Initial Strings : ", ini_string1, ini_string2)

# Using regex()
if re.match('^[0-9]*{content}apos;, ini_string1):
    print ("String1 contains all numbers")
else:
    print ("String1 doesn't contains all numbers")

if re.match('^[0-9]*{content}apos;, ini_string2):
    print ("String2 contains all numbers")
else:
    print ("String2 doesn't contains all numbers")
```

**Output:** 

```
Initial Strings :  1234556 ab123bc
String1 contains all numbers
String2 doesn't contains all numbers
```

**方法#3:使用尝试/异常**

## 蟒蛇 3

```
# Python3 code to demonstrate
# how to check whether string contains
# only numbers or not

# Initialising string
ini_string1 = '1234556'
ini_string2 = 'abc123'

# printing initial string
print ("Initial Strings : ", ini_string1, ini_string2)

# Using try / exception:
try:
    num = int(ini_string1)
    print ("String1 contains only digits")
except:
    print ("String1 doesn'tcontains only digits")

try:
    num = int(ini_string2)
    print ("String2 contains only digits")
except:
    print ("String2 doesn't contains only digits")

```

**Output:** 

```
Initial Strings :  1234556 abc123
String1 contains only digits
String2 doesn't contains only digits
```