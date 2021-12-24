# Python |字符串中的备选案例

> 原文:[https://www . geesforgeks . org/python-字符串中的备选案例/](https://www.geeksforgeeks.org/python-alternate-cases-in-string/)

字符串大小写改变的问题很常见，已经讨论过很多次了。有时，我们可能会遇到这样的问题，我们需要将字符串的奇数字符转换为大写，将偶数位置的字符转换为小写。让我们讨论一下实现这一点的某些方法。
**方法#1:使用 upper() + lower() + loop**
这个任务可以用蛮力的方法来执行，我们迭代字符串，分别使用 upper()和 lower()将奇数元素转换为大写，将偶数元素转换为小写。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Alternate cases in String
# Using upper() + lower() + loop

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + str(test_str))

# Using upper() + lower() + loop
# Alternate cases in String
res = ""
for idx in range(len(test_str)):
    if not idx % 2 :
       res = res + test_str[idx].upper()
    else:
       res = res + test_str[idx].lower()

# printing result
print("The alternate case string is : " + str(res))
```

**Output**

```py
The original string is : geeksforgeeks
The alternate case string is : GeEkSfOrGeEkS

```

**方法 2:使用列表理解**
这是这个问题的缩短的一个线性方法。它使用与上面相同的逻辑，但方式更简洁。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Alternate cases in String
# Using list comprehension

# initializing string
test_str = "geeksforgeeks"

# printing original string
print("The original string is : " + str(test_str))

# Using list comprehension
# Alternate cases in String
res = [ele.upper() if not idx % 2 else ele.lower() for idx, ele in enumerate(test_str)]
res = "".join(res)

# printing result
print("The alternate case string is : " + str(res))
```

**Output**

```py
The original string is : geeksforgeeks
The alternate case string is : GeEkSfOrGeEkS

```