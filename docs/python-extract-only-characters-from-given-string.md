# Python |仅从给定字符串中提取字符

> 原文:[https://www . geesforgeks . org/python-从给定字符串中仅提取字符/](https://www.geeksforgeeks.org/python-extract-only-characters-from-given-string/)

给定一个字符串，任务是从字符串中只提取字母字符。下面给出了几个解决给定问题的方法。

**方法#1:使用`re.split`**

```py
# Python code to demonstrate
# to get characters from string
import re

# initialising string
ini_string = "123()#$ABGFDabcjw"
ini_string2 = "abceddfgh"

# printing strings
print ("initial string : ", ini_string, ini_string2)

# code to find characters in string
res1 = " ".join(re.split("[^a-zA-Z]*", ini_string))
res2 = " ".join(re.split("[^a-zA-Z]*", ini_string2))

# printing resultant string
print ("first string result: ", str(res1))
print ("second string result: ", str(res2))
```

**输出:**

```py
initial string :  123()#$ABGFDabcjw abceddfgh
first string result:   ABGFDabcjw
second string result:  abceddfgh
```

**方法 2:使用`re.fidall`**

```py
# Python code to demonstrate
# to get characters in string
import re

# initialising string
ini_string = "123()#$ABGFDabcjw"
ini_string2 = "abceddfgh"

# printing strings
print ("initial string : \n", ini_string, "\n", ini_string2)

# code to find characters in string
res1 = " ".join(re.findall("[a-zA-Z]+", ini_string))
res2 = " ".join(re.findall("[a-zA-Z]+", ini_string2))

# printing resultant string
print ("first string result: ", str(res1))
print ("second string result: ", str(res2))
```

**输出:**

```py
initial string : 
 123()#$ABGFDabcjw 
 abceddfgh

first string result:  ABGFDabcjw
second string result:  abceddfgh
```

**方法三:使用`isalpha()`**

```py
# Python code to demonstrate
# to get characters in a string
# if present

# initialising string
ini_string = "123()#$ABGFDabcjw"

# printing string and its length
print ("initial string : ", ini_string)

# code to find characters in string
res1 = ""
for i in ini_string:
    if i.isalpha():
        res1 = "".join([res1, i])

# printing resultant string
print ("first result: ", str(res1))
```

**输出:**

```py
initial string :  123()#$ABGFDabcjw
first result:  ABGFDabcjw

```