# Python–将字符串转换为 unicode 字符

> 原文:[https://www . geeksforgeeks . org/python-convert-string-to-unicode-characters/](https://www.geeksforgeeks.org/python-convert-string-to-unicode-characters/)

给定一个字符串，将其字符转换为 unicode 字符。

> **输入** : test_str = 'gfg'
> **输出** : \u0067\u0066\u0067
> **解释**:结果改为单码字符串。
> 
> **输入** : test_str = 'himani'
> **输出**:结果变为单码字符串。

**方法#1:使用 re . sub()+order()+lambda**

在本例中，我们使用 re.sub()执行替换任务，使用 lambda 函数使用 order()执行每个字符的转换任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert String to unicode characters
# using re.sub() + ord() + lambda
import re

# initializing string
test_str = 'geeksforgeeks'

# printing original String
print("The original string is : " + str(test_str))

# using sub() to perform substitutions
# ord() for conversion.
res = (re.sub('.', lambda x: r'\u % 04X' % ord(x.group()), test_str))

# printing result 
print("The unicode converted String : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks
The unicode converted String : \u0067\u0065\u0065\u006B\u0073\u0066\u006F\u0072\u0067\u0065\u0065\u006B\u0073

```

**方法 2:使用 join()+format()+order()**

在这种情况下，unicode 格式字符串的替换任务是使用 format()完成的，order()用于转换。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert String to unicode characters
# using join() + format() + ord()
import re

# initializing string
test_str = 'geeksforgeeks'

# printing original String
print("The original string is : " + str(test_str))

# using format to perform required formatting 
res = ''.join(r'\u{:04X}'.format(ord(chr)) for chr in test_str)

# printing result 
print("The unicode converted String : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks
The unicode converted String : \u0067\u0065\u0065\u006B\u0073\u0066\u006F\u0072\u0067\u0065\u0065\u006B\u0073

```