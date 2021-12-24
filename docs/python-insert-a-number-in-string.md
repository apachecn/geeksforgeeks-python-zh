# Python |在字符串中插入数字

> 原文:[https://www . geesforgeks . org/python-插入字符串中的数字/](https://www.geeksforgeeks.org/python-insert-a-number-in-string/)

有时，在处理字符串时，我们可能会遇到一个问题，即我们可能有一个数值变量，它的值不断变化，我们需要打印包含该数字的字符串。字符串和数字是不同的数据类型，必须用不同的方法来解决。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用类型转换**
执行此任务的最简单方法是使用基本类型转换将整数显式转换为字符串数据类型，并将其添加到适当的位置。

```
# Python3 code to demonstrate working of
# Inserting a number in string 
# Using type conversion

# initializing string 
test_str = "Geeks"

# initializing number
test_int = 4 

# printing original string 
print("The original string is : " + test_str)

# printing number
print("The original number : " + str(test_int))

# using type conversion
# Inserting number in string 
res = test_str + str(test_int) + test_str

# printing result 
print("The string after adding number is  : " + str(res))
```

**Output :**

```
The original string is : Geeks
The original number : 4
The string after adding number is  : Geeks4Geeks

```