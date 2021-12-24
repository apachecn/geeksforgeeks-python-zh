# Python |十进制到二进制列表转换

> 原文:[https://www . geesforgeks . org/python-十进制到二进制列表转换/](https://www.geeksforgeeks.org/python-decimal-to-binary-list-conversion/)

二进制列表到十进制数的转换已经在[之前的文章](https://www.geeksforgeeks.org/binary-decimal-vice-versa-python/)中讨论过。本文旨在介绍一些与之相反的简写，即二进制到十进制的转换。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+ `format()`**
在该方法中，十进制到二进制的转换由格式函数处理。转换到列表的逻辑由列表理解功能完成。

```py
# Python3 code to demonstrate 
# decimal to binary number conversion
# using format() + list comprehension

# initializing number 
test_num = 38

# printing original number
print ("The original number is : " + str(test_num))

# using format() + list comprehension
# decimal to binary number conversion 
res = [int(i) for i in list('{0:0b}'.format(test_num))]

# printing result 
print ("The converted binary list is : " +  str(res))
```

**Output:**

```py
The original number is : 38
The converted binary list is : [1, 0, 0, 1, 1, 0]

```

**方法 2:使用`bin()` +列表理解**
内置的函数 bin 执行转换为二进制的功能，列表理解处理将二进制数转换为列表的逻辑。

```py
# Python3 code to demonstrate 
# decimal to binary number conversion
# using bin() + list comprehension

# initializing number 
test_num = 38

# printing original number
print ("The original number is : " + str(test_num))

# using bin() + list comprehension
# decimal to binary number conversion 
res = [int(i) for i in bin(test_num)[2:]]

# printing result 
print ("The converted binary list is : " +  str(res))
```

**Output:**

```py
The original number is : 38
The converted binary list is : [1, 0, 0, 1, 1, 0]

```