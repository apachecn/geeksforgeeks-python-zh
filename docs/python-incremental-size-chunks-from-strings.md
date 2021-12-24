# Python–字符串的增量大小块

> 原文:[https://www . geeksforgeeks . org/python-增量大小-从字符串中获取组块/](https://www.geeksforgeeks.org/python-incremental-size-chunks-from-strings/)

给定一个字符串，将其拆分为大小递增的连续列表。

> **输入**:test _ str = ' geek forgeks is best '
> **输出** : ['g '，' ee '，' kfo '，' rgee '，' ks is '，' best']
> **解释**:列表中字符大小增加。
> 
> **输入**:test _ str = ' geek forgeeks '
> **输出** : ['g '，' ee '，' kfo '，' rgee '，' ks']
> **解释**:列表中字符大小增加。

**方法#1:使用循环+切片**

在本文中，我们使用字符串切片执行获取块的任务，并在迭代过程中不断增加块的大小。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Incremental Size Chunks from Strings
# Using loop + slicing

# initializing string
test_str = 'geekforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

res = []
idx = 1
while True:
    if len(test_str) > idx:

        # chunking
        res.append(test_str[0 : idx])
        test_str = test_str[idx:]
        idx += 1
    else:
        res.append(test_str)
        break

# printing result 
print("The Incremental sized Chunks : " + str(res)) 
```

**Output**

```
The original string is : geekforgeeks is best for geeks
The Incremental sized Chunks : ['g', 'ee', 'kfo', 'rgee', 'ks is', ' best ', 'for gee', 'ks']

```

**方法 2:使用生成器+切片**

在这种情况下，我们像上面的方法一样执行切片，不同的是块是使用生成器表达式呈现的，每个块在运行时循环产生。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Incremental Size Chunks from Strings
# Using generator + slicing 

# generator function 
def gen_fnc(test_str):
    strt = 0
    stp = 1
    while test_str[strt : strt + stp]:

        # return chunks runtime while looping
        yield test_str[strt : strt + stp]
        strt += stp
        stp += 1

# initializing string
test_str = 'geekforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# calling fnc.
res = list(gen_fnc(test_str))

# printing result 
print("The Incremental sized Chunks : " + str(res)) 
```

**Output**

```
The original string is : geekforgeeks is best for geeks
The Incremental sized Chunks : ['g', 'ee', 'kfo', 'rgee', 'ks is', ' best ', 'for gee', 'ks']

```