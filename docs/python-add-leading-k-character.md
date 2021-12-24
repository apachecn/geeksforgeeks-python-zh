# Python |添加前导 K 字符

> 原文:[https://www . geesforgeks . org/python-add-leader-k-character/](https://www.geeksforgeeks.org/python-add-leading-k-character/)

有时，在字符串操作过程中，我们会遇到一个问题，需要根据需要在字符串中填充或添加前导 K。这个问题可能发生在 web 开发中。在许多情况下，用人手解决这个问题会很方便。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`rjust()`**
rjust 函数提供了一种执行该特定任务的单线方式。因此可以很容易地应用于任何需要填充的字符串。我们可以指定所需的填充量。

```
# Python3 code to demonstrate 
# Add leading K character
# using rjust() 

# initializing string 
test_string = 'GFG'

# printing original string 
print("The original string : " + str(test_string)) 

# No. of zeros required 
N = 4

# initializing K 
K = 'M'

# using rjust() 
# Add leading K character
res = test_string.rjust(N + len(test_string), K) 

# print result 
print("The string after adding leading K : " + str(res)) 
```

**Output :**

```
The original string : GFG
The string after adding leading K : MMMMGFG

```