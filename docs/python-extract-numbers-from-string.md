# Python |从字符串中提取数字

> 原文:[https://www . geesforgeks . org/python-extract-numbers-from-string/](https://www.geeksforgeeks.org/python-extract-numbers-from-string/)

很多时候，在处理字符串时，我们会遇到这样一个问题，我们需要获得所有的数字出现。这种类型的问题通常发生在竞争性编程和 web 开发中。让我们讨论一下解决这个问题的某些方法。

**方法一:使用列表理解+`isdigit()`+`split()`+**
这个问题可以通过使用 split 函数将字符串转换为 list，然后使用 list 理解来解决，List 理解可以帮助我们遍历列表，isdigit 函数有助于从字符串中获取数字。

```py
# Python3 code to demonstrate
# getting numbers from string 
# using List comprehension + isdigit() +split()

# initializing string 
test_string = "There are 2 apples for 4 persons"

# printing original string 
print("The original string : " + test_string)

# using List comprehension + isdigit() +split()
# getting numbers from string 
res = [int(i) for i in test_string.split() if i.isdigit()]

# print result
print("The numbers list is : " + str(res))
```

**Output :**

```py
The original string : There are 2 apples for 4 persons
The numbers list is : [2, 4]

```