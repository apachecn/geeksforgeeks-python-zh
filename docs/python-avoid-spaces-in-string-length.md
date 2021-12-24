# Python–避免字符串长度中的空格

> 原文:[https://www . geesforgeks . org/python-避免字符串长度中的空格/](https://www.geeksforgeeks.org/python-avoid-spaces-in-string-length/)

给定一个字符串，计算除空格以外的所有字符。

> **输入**:test _ str = ' geeksforgeeks 33 best '
> **输出** : 19
> **说明**:共计 19 个字符。
> 
> **输入**:test _ str = ' geeksforgeeks best '
> **输出** : 17
> **说明**:除空格外字符总数为 17。

**方法#1:使用 isspace() + sum()**

在本例中，我们使用 isspace()和 not 运算符检查每个字符是否等于 not space()，sum()用于检查频率。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Avoid Spaces in Characters Frequency
# Using isspace() + sum()

# initializing string
test_str = 'geeksforgeeks 33 is   best'

# printing original string
print("The original string is : " + str(test_str))

# isspace() checks for space 
# sum checks count 
res = sum(not chr.isspace() for chr in test_str)

# printing result 
print("The Characters Frequency avoiding spaces : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks 33 is   best
The Characters Frequency avoiding spaces : 21

```

**方法 2:使用 sum() + len() + map() + split()**

在本文中，我们对空格执行拆分并提取没有空格的单词，然后使用 len()计算的长度()使用 map()扩展到每个单词，使用 sum()计算的所有长度的总和就是最终结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Avoid Spaces in Characters Frequency
# Using sum() + len() + map() + split()

# initializing string
test_str = 'geeksforgeeks 33 is   best'

# printing original string
print("The original string is : " + str(test_str))

# len() finds individual word Frequency 
# sum() extracts final Frequency
res = sum(map(len, test_str.split()))

# printing result 
print("The Characters Frequency avoiding spaces : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks 33 is   best
The Characters Frequency avoiding spaces : 21

```