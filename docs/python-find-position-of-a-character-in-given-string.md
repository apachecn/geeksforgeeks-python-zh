# Python |查找给定字符串中字符的位置

> 原文:[https://www . geesforgeks . org/python-查找给定字符串中字符的位置/](https://www.geeksforgeeks.org/python-find-position-of-a-character-in-given-string/)

给定一个字符串和一个字符，您的任务是找到该字符在字符串中的第一个位置。这些类型的问题是非常有竞争力的编程，您需要定位字符串中字符的位置。
我们来讨论几个解决问题的方法。
**方法#1:使用天真方法**

## 蟒蛇 3

```
# Python3 code to demonstrate
# to find the first position of the character
# in a given string

# Initializing string
ini_string = 'abcdef'

# Character to find
c = "b"
# printing initial string and character
print ("initial_string : ", ini_string, "\ncharacter_to_find : ", c)

# Using Naive Method
res = None
for i in range(0, len(ini_string)):
    if ini_string[i] == c:
        res = i + 1
        break

if res == None:
    print ("No such character available in string")
else:
    print ("Character {} is present at {}".format(c, str(res)))
```

**Output:** 

```
initial_string :  abcdef 
character_to_find :  b
Character b is present at 2
```

**方法 2:使用**查找
如果字符不存在，该方法返回-1。

## 蟒蛇 3

```
# Python3 code to demonstrate
# to find first position of character
# in a given string

# Initializing string
ini_string = 'abcdef'
ini_string2 = 'xyze'

# Character to find
c = "b"
# printing initial string and character
print ("initial_strings : ", ini_string, " ",
        ini_string2, "\ncharacter_to_find : ", c)

# Using find Method
res1 = ini_string.find(c)
res2 = ini_string2.find(c)

if res1 == -1:
    print ("No such character available in string {}".format(
                                                ini_string))
else:
    print ("Character {} in string {} is present at {}".format(
                                 c, ini_string, str(res1 + 1)))

if res2 == -1:
    print ("No such character available in string {}".format(
                                               ini_string2))
else:
    print ("Character {} in string {} is present at {}".format(
                                c, ini_string2, str(res2 + 1)))
```

**输出:**

```
initial_strings :  abcdef   xyze  
character_to_find :  b
Character b in string abcdef is present at 2
No such character available in string xyze
```

**方法#3:使用索引()**
如果字符不存在
该方法会引发值错误

## 蟒蛇 3

```
# Python3 code to demonstrate
# to find first position of character
# in a given string

# Initializing string
ini_string1 = 'xyze'

# Character to find
c = "b"
# printing initial string and character
print ("initial_strings : ", ini_string1,
             "\ncharacter_to_find : ", c)

# Using index Method
try:
    res = ini_string1.index(c)
    print ("Character {} in string {} is present at {}".format(
                                  c, ini_string1, str(res + 1)))
except ValueError as e:
    print ("No such character available in string {}".format(ini_string1))
```

**输出:**

```
initial_strings :  xyze  
character_to_find :  b
No such character available in string xyze
```