# Python |将数字转换为整数列表

> 原文:[https://www . geesforgeks . org/python-将数字转换为整数列表/](https://www.geeksforgeeks.org/python-convert-number-to-list-of-integers/)

数据类型的相互转换是编程中非常常见的问题。有时我们需要将一个数字转换成整数列表，但我们不希望花费几行代码来完成。因此，使用人手不足的方法来完成这项任务就变得很方便了。让我们来讨论一下如何实现这一点。

**方法#1:使用列表理解**
列表理解可以作为幼稚方法的较长格式的简写。在这种方法中，我们将数字转换成字符串，然后提取它的每个字符并将其重新转换成整数。

```py
# Python3 code to demonstrate 
# conversion of number to list of integers
# using list comprehension

# initializing number 
num = 2019

# printing number 
print ("The original number is " + str(num))

# using list comprehension
# to convert number to list of integers
res = [int(x) for x in str(num)]

# printing result 
print ("The list from number is " + str(res))
```

**输出:**

```py
The original number is 2019
The list from number is [2, 0, 1, 9]
```

**方法 2:使用`map()`**
`map` 函数可以执行以下任务:将每个字符串转换后的数字转换为所需的整数值，再转换为列表格式。

```py
# Python3 code to demonstrate 
# conversion of number to list of integers
# using map()

# initializing number 
num = 2019

# printing number 
print ("The original number is " + str(num))

# using map()
# to convert number to list of integers
res = list(map(int, str(num)))

# printing result 
print ("The list from number is " + str(res))
```

**输出:**

```py
The original number is 2019
The list from number is [2, 0, 1, 9]
```