# Python–字符串中的所有子字符串频率

> 原文:[https://www . geesforgeks . org/python-all-substrings-in-frequency-in-string/](https://www.geeksforgeeks.org/python-all-substrings-frequency-in-string/)

给定一个字符串，提取所有唯一的子字符串及其频率。

> **输入** : test_str = "亚的斯亚贝巴"
> **输出** : {'a': 3，' ab': 2，' aba': 2，' abab': 1，'亚的斯亚贝巴':1，' b': 2，' ba': 2，' bab': 1，' baba': 1}
> **解释**:提取其频率的所有子字符串。
> 
> **输入**:test _ str = " GF "
> **输出** : {'G': 2、' GF': 2、' GFG': 1、' GF': 1、' F': 2、' FG': 1、' FGF': 1}
> **解释**:提取所有子串及其频率。

**方法一:使用循环+列表理解**

上述功能的组合可以用来解决这个问题。在这种情况下，我们首先使用列表理解提取所有子字符串，然后使用循环来增加频率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# All substrings Frequency in String
# Using loop + list comprehension

# initializing string
test_str = "abababa"

# printing original string
print("The original string is : " + str(test_str))

# list comprehension to extract substrings
temp = [test_str[idx: j] for idx in range(len(test_str))
       for j in range(idx + 1, len(test_str) + 1)]

# loop to extract final result of frequencies
res = {}
for idx in temp:
     if idx not in res.keys():
             res[idx] = 1
     else:
             res[idx] += 1

# printing result 
print("Extracted frequency dictionary : " + str(res)) 
```

**Output**

```py
The original string is : abababa
Extracted frequency dictionary : {'a': 4, 'ab': 3, 'aba': 3, 'abab': 2, 'ababa': 2, 'ababab': 1, 'abababa': 1, 'b': 3, 'ba': 3, 'bab': 2, 'baba': 2, 'babab': 1, 'bababa': 1}

```

**方法 2:使用列表理解**

这是执行这项任务的另一种方式。在这种情况下，我们完成了单嵌套列表理解中提取子串和计算频率的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# All substrings Frequency in String
# Using list comprehension

# initializing string
test_str = "abababa"

# printing original string
print("The original string is : " + str(test_str))

# list comprehension to extract substrings and frequency
res = dict()
for ele in [test_str[idx: j] for idx in range(len(test_str)) for j in range(idx + 1, len(test_str) + 1)]:
    res[ele] = 1 if ele not in res.keys() else res[ele] + 1             

# printing result 
print("Extracted frequency dictionary : " + str(res)) 
```

**Output**

```py
The original string is : abababa
Extracted frequency dictionary : {'a': 4, 'ab': 3, 'aba': 3, 'abab': 2, 'ababa': 2, 'ababab': 1, 'abababa': 1, 'b': 3, 'ba': 3, 'bab': 2, 'baba': 2, 'babab': 1, 'bababa': 1}

```