# Python–在字符串中的数字和字母之间添加空格

> 原文:[https://www . geesforgeks . org/python-add-数字和字母之间的空格-字符串/](https://www.geeksforgeeks.org/python-add-space-between-numbers-and-alphabets-in-string/)

给定一个由数字和字符串组成的字符串，在它们之间添加空格。

> **输入**:test _ str = ' ge3eks 4 geeks is 1 for 10 geek '
> **输出**:ge 3 eks 4 geek is 1 for 10 geek
> **解释**:数字与字符分开。
> 
> **输入**:test _ str = ' ge3eks 4 geeks '
> **输出** : ge 3 eks 4 geeks
> **解释**:数字与字符之间用空格隔开。

**方法#1:使用正则表达式+sub()+λ**

在本例中，我们通过适当的正则表达式执行查找字母的任务，然后使用 sub()进行替换，lambda 执行在两者之间添加空格的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Add space between Numbers and Alphabets in String
# using regex + sub() + lambda
import re

# initializing string
test_str = 'geeks4geeks is1for10geeks'

# printing original String
print("The original string is : " + str(test_str))

# using sub() to solve the problem, lambda used tp add spaces 
res = re.sub("[A-Za-z]+", lambda ele: " " + ele[0] + " ", test_str)

# printing result 
print("The space added string : " + str(res)) 
```

**Output**

```
The original string is : geeks4geeks is1for10geeks
The space added string :  geeks 4 geeks   is 1 for 10 geeks 

```

**方法 2:使用 regex + sub()**

这是解决的方法之一。在这种情况下，我们寻找数字而不是字母来执行分离任务，通过使用数字的类似方法是添加空格的搜索标准。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Add space between Numbers and Alphabets in String
# using regex + sub()
import re

# initializing string
test_str = 'geeks4geeks is1for10geeks'

# printing original String
print("The original string is : " + str(test_str))

# using sub() to solve the problem, lambda used tp add spaces 
res = re.sub('(\d+(\.\d+)?)', r' \1 ', test_str)

# printing result 
print("The space added string : " + str(res)) 
```

**Output**

```
The original string is : geeks4geeks is1for10geeks
The space added string : geeks 4 geeks is 1 for 10 geeks

```