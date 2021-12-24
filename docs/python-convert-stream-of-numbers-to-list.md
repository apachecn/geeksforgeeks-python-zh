# Python |将数字流转换为列表

> 原文:[https://www . geesforgeks . org/python-convert-numbers-stream-to-list/](https://www.geeksforgeeks.org/python-convert-stream-of-numbers-to-list/)

有时，我们可能会遇到这样一个问题，给我们一串用空格分隔的数字，目标是将它们转换成数字列表。这种类型的问题可能发生在普通的日编程或竞争编程中。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`list() + split()`**
可以通过使用简单的`split`函数将空格分隔的数字转换为列表，该函数将字符串转换为数字列表，从而解决我们的问题。

```
# Python3 code to demonstrate working of
# Convert Stream of numbers to list
# Using list() + split()

# initializing string 
test_str = "10 12 3 54 6 777 443"

# printing original string 
print("The original string is : " + test_str)

# Using list() + split()
# Convert Stream of numbers to list
res = list(test_str.split())

# printing result 
print("The list of stream of numbers : " + str(res))
```

**Output :**

```
The original string is : 10 12 3 54 6 777 443
The list of stream of numbers : ['10', '12', '3', '54', '6', '777', '443']

```