# Python–多行字符串的水平连接

> 原文:[https://www . geesforgeks . org/python-水平-多行字符串串联/](https://www.geeksforgeeks.org/python-horizontal-concatenation-of-multiline-strings/)

给定多行字符串对，水平执行连接。

**示例:**

> **输入**:
> test _ str 1 = '
> 极客为
> 极客"'，
> test _ str 2 = '
> 为
> best"'
> **输出** :
> 极客为 is
> 极客为
> **解释**:第一行与第二串第一行连接，“极客为”- >“是”。
> 
> **输入**:
> test _ str 1 = '
> 极客为“
> test _ str 2 = '
> 极客为“
> **输出** :
> 极客为极客
> **解释**:第一行与第二串第一行连接，“极客”为“- >“极客”。

**方法一:使用 zip() + split() + join() +列表理解**

在本例中，我们使用 [split()](https://www.geeksforgeeks.org/python-string-split/) 通过“\n”执行拆分任务，并使用 [zip()](https://www.geeksforgeeks.org/zip-in-python/) 将它们配对在一起。下一步是使用“\n”连接水平方向的压缩字符串和[连接()](https://www.geeksforgeeks.org/join-function-python/)。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Horizontal Concatenation of Multiline Strings
# Using zip() + split() + join() + list comprehension

# initializing strings
test_str1 = '''
geeks 4
geeks'''

test_str2 = '''
is
best'''

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# split lines
splt_lines = zip(test_str1.split('\n'), test_str2.split('\n'))

# horizontal join
res = '\n'.join([x + y for x, y in splt_lines])

# printing result
print("After String Horizontal Concatenation : " + str(res))
```

**Output**

```py
The original string 1 is : 
geeks 4
geeks
The original string 2 is : 
is
best
After String Horizontal Concatenation : 
geeks 4is
geeksbest

```

**方法 2:使用 map() +运算符. add + join()**

在本例中，我们使用 [map()](https://www.geeksforgeeks.org/python-map-function/) 来借助 add()执行拼接，split()用于通过“\n”执行初始拆分。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Horizontal Concatenation of Multiline Strings
# Using map() + operator.add + join()
from operator import add

# initializing strings
test_str1 = '''
geeks 4
geeks'''
test_str2 = '''
is
best'''

# printing original strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# using add to concat, map() to concat each lines zipped
res = '\n'.join(map(add, test_str1.split('\n'), test_str2.split('\n')))

# printing result
print("After String Horizontal Concatenation : " + str(res))
```

**Output**

```py
The original string 1 is : 
geeks 4
geeks
The original string 2 is : 
is
best
After String Horizontal Concatenation : 
geeks 4is
geeksbest

```