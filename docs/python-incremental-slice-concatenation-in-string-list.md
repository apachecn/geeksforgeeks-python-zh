# Python–字符串列表中的增量切片串联

> 原文:[https://www . geesforgeks . org/python-增量-切片-字符串串联-列表/](https://www.geeksforgeeks.org/python-incremental-slice-concatenation-in-string-list/)

给定一个字符串列表，通过增加每个字符串的大小来执行字符串串联的任务。

**示例:**

> **输入** : test_list = ['gfg '，' for '，' all '，' geek ']，
> **输出**:gfoalgeek
> **解释** : g，fo，all，geek - >由每个字符串串联而成【递增顺序】。
> 
> **输入** : test_list = ['gfg '，' for '，'极客']，
> **输出** : gfogee
> **解释** : g，fo，gee - >从每个字符串串联【递增顺序】。

**方法#1:使用 loop +** [**切片**](https://www.geeksforgeeks.org/string-slicing-in-python/)

在这种情况下，使用循环，通过在每次通过时增加计数器的切片来迭代和连接每个字符串。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Incremental Slice concatenation in String list
# Using loop + slicing

# initializing list
test_list = ['gfg', 'for', 'all', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

res = ''
for idx in range(len(test_list)):

    # Incremental slicing
    res += test_list[idx][:idx + 1]

# printing result 
print("Incremental sliced concatenated string : " + str(res))
```

**Output**

```py
The original list is : ['gfg', 'for', 'all', 'geeks']
Incremental sliced concatenated string : gfoallgeek

```

**方法 2:使用 join() +列表理解**

在这种情况下，连接任务使用 join()完成，迭代任务使用列表理解来提供速记。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Incremental Slice concatenation in String list
# Using join() + list comprehension

# initializing list
test_list = ['gfg', 'for', 'all', 'geeks']

# printing original list
print("The original list is : " + str(test_list))

# join performs concatenation
res = ''.join([test_list[idx][:idx + 1] for idx in range(len(test_list))])

# printing result 
print("Incremental sliced concatenated string : " + str(res))
```

**Output**

```py
The original list is : ['gfg', 'for', 'all', 'geeks']
Incremental sliced concatenated string : gfoallgeek

```