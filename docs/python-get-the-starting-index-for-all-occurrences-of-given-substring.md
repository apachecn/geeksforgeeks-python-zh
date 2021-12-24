# Python |获取给定子串所有出现的起始索引

> 原文:[https://www . geesforgeks . org/python-获取给定子串的所有出现的起始索引/](https://www.geeksforgeeks.org/python-get-the-starting-index-for-all-occurrences-of-given-substring/)

给定一个字符串和一个子字符串，任务是找出给定子字符串在字符串中所有出现的起始索引。让我们讨论几个解决给定任务的方法。

**方法#1:使用天真法**

```
# Python3 code to demonstrate
# to find all occurrences of substring in
# a string

# Initialising string
ini_string = 'xbzefdgstbzefzexezef'

# Initialising sub-string
sub_string = 'zef'

# Printing initial string and sub-string
print ("initial_strings : ", ini_string, "\nsubstring : ", sub_string)

res = []
flag = 0
k = 0

# Finding all occurrences of substring
# in a string using Naive method
for i in range(0, len(ini_string)):
    k = i
    flag = 0
    for j in range(0, len(sub_string)):
        if ini_string[k] != sub_string[j]:
            flag = 1
        if flag:
            break
        k = k + 1
    if flag == 0:
        res.append(i)

# printing result(
print ("resultant positions", str(res))
```

**输出:**

```
initial_strings :  xbzefdgstbzefzexezef 
substring :  zef
resultant positions [2, 10, 17]

```