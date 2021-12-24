# Python–长度条件串联

> 原文:[https://www . geesforgeks . org/python-length-conditional-concation/](https://www.geeksforgeeks.org/python-length-conditional-concatenation/)

给定一个字符串列表，执行长度大于 k 的字符串的串联

> **输入**:test _ list =[“Gfg”，“is”，“Best”，“for”，“CS”，“Everything”]，K = 3
> **输出** : BestEverything
> **解释**:长度为> 3 的所有元素串联。
> 
> **输入**:test _ list =[“Gfg”，‘is’，‘Best’，‘for’，‘CS’，‘Everything’]，K = 1
> **输出**:gfgissbestforseverything
> **解释**:长度为> 1 的所有元素串联。

**方法#1:使用 loop + len()**

这为解决这个问题提供了一种粗暴的方法。在本文中，我们使用 len()对每个字符串进行迭代，如果字符串长度大于 K，则执行串联。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Length Conditional Concatenation
# Using loop + len()

# initializing lists
test_list = ["Gfg", 'is', "Best", 'for', 'CS', 'Everything']

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 2

# loop to run through all the elements
res = ''
for ele in test_list:

    # using len() to check for length
    if len(ele) > 2:
        res += ele

# printing result 
print("String after Concatenation : " + str(res))
```

**Output**

```py
The original list : ['Gfg', 'is', 'Best', 'for', 'CS', 'Everything']
String after Concatenation : GfgBestforEverything

```

**方法 2:使用 join()+filter()+lambda+len()**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 join()执行连接，使用 len()将 filter 和 lambda 用于条件检查。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Length Conditional Concatenation
# Using join() + filter() + lambda + len()

# initializing lists
test_list = ["Gfg", 'is', "Best", 'for', 'CS', 'Everything']

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 2

# join() performing Concatenation of required strings
res = ''.join(filter(lambda ele: len(ele) > K, test_list))

# printing result 
print("String after Concatenation : " + str(res))
```

**Output**

```py
The original list : ['Gfg', 'is', 'Best', 'for', 'CS', 'Everything']
String after Concatenation : GfgBestforEverything

```