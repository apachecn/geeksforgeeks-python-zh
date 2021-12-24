# Python–提取两个子字符串之间的字符串

> 原文:[https://www . geesforgeks . org/python-extract-两个子字符串之间的字符串/](https://www.geeksforgeeks.org/python-extract-string-between-two-substrings/)

给定一个字符串和两个子字符串，编写一个 Python 程序来提取找到的两个子字符串之间的字符串。

> **输入:**test _ str =“Gfg 最适合极客和 CS”，sub 1 =“is”，sub 2 =“and”
> 
> **输出:**最适合极客
> 
> **解释:**极客最好是在 is 和‘and’之间
> 
> **输入:**test _ str =“Gfg 最适合极客和 CS”，sub1 =“适合”，sub2 =“和”
> 
> **输出:**极客
> 
> **解释:**极客介于 for 和‘and’之间

**方法#1:使用** [**指数()**](https://www.geeksforgeeks.org/python-list-index/) **+** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们使用 index()获取两个子字符串的索引，然后使用循环在索引内迭代，以找到它们之间所需的字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working
# of Extract string between 2 substrings
# Using loop + index()

# initializing string
test_str = "Gfg is best for geeks and CS"

# printing original string
print("The original string is : " + str(test_str))

# initializing substrings
sub1 = "is"
sub2 = "and"

# getting index of substrings
idx1 = test_str.index(sub1)
idx2 = test_str.index(sub2)

res = ''
# getting elements in between
for idx in range(idx1 + len(sub1) + 1, idx2):
    res = res + test_str[idx]

# printing result
print("The extracted string : " + res)
```

**输出:**

```py
The original string is : Gfg is best for geeks and CS
The extracted string : best for geeks 
```

**方法 2:使用** [**指数()**](https://www.geeksforgeeks.org/python-list-index/) **+** [**串切片**](https://www.geeksforgeeks.org/string-slicing-in-python/)

类似于上面的方法，只是使用字符串切片来执行切片任务，以提供更紧凑的解决方案。

## 蟒蛇 3

```py
# Python3 code to demonstrate working 
# of Extract string between 2 substrings
# Using index() + string slicing

# initializing string
test_str = "Gfg is best for geeks and CS"

# printing original string
print("The original string is : " + str(test_str))

# initializing substrings
sub1 = "is"
sub2 = "and"

# getting index of substrings
idx1 = test_str.index(sub1)
idx2 = test_str.index(sub2)

# length of substring 1 is added to
# get string from next character
res = test_str[idx1 + len(sub1) + 1: idx2]

# printing result
print("The extracted string : " + res)
```

**输出:**

```py
The original string is : Gfg is best for geeks and CS
The extracted string : best for geeks 
```