# Python–在案例转换之间添加 K

> 原文:[https://www . geesforgeks . org/python-add-k-格间转换/](https://www.geeksforgeeks.org/python-add-k-between-case-shifts/)

给定一个字符串，当发生大小写转换时加 K。

> **输入** : test_str = 'GeeKSforGeEKs '，K = ' *
> **输出**:G * ee * KS *为*G*e*EK*s
> **解释**:G 后出现小写字母 e，中间插入*号。每次插入都一样。
> 
> **输入** : test_str = 'GeeKS '，K = ' *
> **输出** : G*ee*KS
> **解释**:插在大小写切换处，如上所述。

**方法#1:使用 loop + isupper() + islower()**

在这种情况下，我们对每个元素进行迭代，并在每个元素上检查下一个是否属于不同的情况，如果是，则在连接处添加 K。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Add K between case shifts
# Using loop + isupper() + islower()
import re

# initializing string
test_str = 'GeeKSforGeEKs'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = '^'

res = ""
for idx in range(0, len(test_str) - 1):
    # checking for case shift
    if test_str[idx].isupper() and test_str[idx + 1].islower() or test_str[idx].islower() and test_str[idx + 1].isupper():
        res = res + test_str[idx] + K
    else:
        res = res + test_str[idx]
res = res + test_str[-1]

# printing result
print("String after alteration : " + str(res))
```

**Output**

```
The original string is : GeeKSforGeEKs
String after alteration : G^ee^KS^for^G^e^EK^s

```

**方法 2:使用列表理解**

解决这个问题的另一种方法，只是提供了上述方法的简写。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Add K between case shifts
# Using loop + isupper() + islower()

# initializing string
test_str = 'GeeKSforGeEKs'

# printing original string
print("The original string is : " + str(test_str))

# initializing K
K = '^'

# join() to get result string
res = ''.join([test_str[idx] + K if (test_str[idx].isupper() and test_str[idx + 1].islower()) or
               (test_str[idx].islower() and test_str[idx + 1].isupper()) else test_str[idx] for idx in range(0, len(test_str) - 1)])

res += test_str[-1]

# printing result
print("String after alteration : " + str(res))
```

**Output**

```
The original string is : GeeKSforGeEKs
String after alteration : G^ee^KS^for^G^e^EK^s

```