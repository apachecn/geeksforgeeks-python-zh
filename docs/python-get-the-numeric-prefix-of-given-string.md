# Python |获取给定字符串的数字前缀

> 原文:[https://www . geesforgeks . org/python-get-the-numeric-prefix-of-given-string/](https://www.geeksforgeeks.org/python-get-the-numeric-prefix-of-given-string/)

给定一个字符串。任务是打印字符串中的数字前缀(如果字符串中有)。下面给出了几个解决任务的方法。

**方法#1:使用天真法**

```
# Python code to demonstrate
# to get numeric prefix in string
# if present

# initialising string
ini_string = "123abcjw"
ini_string2 = "abceddfgh"

# printing string and its length
print ("initial string : ", ini_string, ini_string2)

# code to find numeric prefix in string
res1 = ''.join(c for c in ini_string if c in '0123456789')
res2 = ''.join(c for c in ini_string2 if c in '0123456789')

# printing resultant string
print ("first string result: ", str(res1))
print ("second string result: ", str(res2))
```

**输出:**

```
initial string :  123abcjw abceddfgh
first string result:  123
second string result:

```