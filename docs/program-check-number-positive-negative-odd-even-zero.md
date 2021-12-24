# 检查一个数字是否为正、负、奇、偶、零的程序

> 原文:[https://www . geesforgeks . org/program-check-number-正数-负数-奇数-偶数-零/](https://www.geeksforgeeks.org/program-check-number-positive-negative-odd-even-zero/)

**先决条件:**[Python 中的循环](https://www.geeksforgeeks.org/loops-in-python/)

检查一个数是正的、负的、奇数、偶数还是零。这个问题是使用 if…elif…else 和嵌套的 if…else 语句解决的。
**进场:**

*   如果一个数大于零，它就是正数。我们在 if 的表达式中检查这个。
*   如果为假，则该数字要么为零，要么为负。
*   这也在随后的表达式中得到检验。
*   在奇数和偶数的情况下，如果一个数能被 2 完全整除，它就是偶数。

示例:

```py
Input : 10
Output :
Positive number
10 is Even

```

```py
Input : 0
Output : 0 is Even

```

```py
# Python Code to check if a number is
# Positive, Negative, Odd, Even, Zero 
# Using if...elif...else
num = 10
if num > 0:
   print("Positive number")
elif num == 0:
   print("Zero")
else:
   print("Negative number")

# Checking for odd and even
if (num % 2) == 0:
   print("{0} is Even".format(num))
else:
   print("{0} is Odd".format(num))
```

```py
Output:
Positive number
10 is Even

```

```py
# Python Code to check if a number is
# Positive, Negative, Odd, Even, Zero
# Using Nested if
num = 20
if num >= 0:
   if num == 0:
       print("Zero")
   else:
       print("Positive number")
else:
   print("Negative number")

# Cchecking for odd and even
if (num % 2) == 0:
   print("{0} is Even".format(num))
else:
   print("{0} is Odd".format(num))
```

```py
Output:
Positive number
20 is Even

```