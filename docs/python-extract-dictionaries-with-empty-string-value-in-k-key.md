# Python–提取 K 键中字符串值为空的字典

> 原文:[https://www . geesforgeks . org/python-extract-dictionary-with-empty-string-value-in-k-key/](https://www.geeksforgeeks.org/python-extract-dictionaries-with-empty-string-value-in-k-key/)

给定字典列表，提取所有具有空字符串作为特定键值的字典。

> **输入**:test _ list =[{“Gfg”:“4”，“是”:“好”，“最好”:“1”}，{“Gfg”:“9”，“是”:“CS”，“最好”:“10”}]，K =“Gfg”
> **输出** : []
> **解释**:无“Gfg”键为空。
> 
> **输入**:test _ list =[{“Gfg”:“”、“”:“好”、“最好”:“1”}、{“Gfg”:“9”、“是”:“CS”、“最好”:“10”}]、K =“Gfg”
> **输出**:[{“Gfg”:“”、“:“好”、“最好”:“1”}]
> **解释**:字典中带空的“Gfg”提取出来。

**方法一:使用列表理解**

这是执行这项任务的方法之一。在这种情况下，我们在所有字典中运行一个循环，并检查键的空字符串值。所有这些都是在列表理解而不是循环中编译的。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract dictionaries with Empty String value in K key
# Using list comprehension

# initializing lists
test_list = [{"Gfg" : "4", "is" : "good", "best" : "1"},
             {"Gfg" : "", "is" : "better", "best" : "8"},
             {"Gfg" : "9", "is" : "CS", "best" : "10"}]

# printing original list
print("The original list : " + str(test_list))

# initializing K key 
K = "Gfg"

# using list comprehension to fetch empty string key's dictionaries
res = [sub for sub in test_list if sub[K] == '']

# printing result 
print("The extracted dictionaries : " + str(res))
```

**Output**

```py
The original list : [{'Gfg': '4', 'is': 'good', 'best': '1'}, {'Gfg': '', 'is': 'better', 'best': '8'}, {'Gfg': '9', 'is': 'CS', 'best': '10'}]
The extracted dictionaries : [{'Gfg': '', 'is': 'better', 'best': '8'}]

```

**方法 2:使用过滤器()+λ**

这是执行这项任务的另一种方式。在本文中，我们使用 filter()和 lambda 的功能和迭代提取所有空值键的字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract dictionaries with Empty String value in K key
# Using filter() + lambda

# initializing lists
test_list = [{"Gfg" : "4", "is" : "good", "best" : "1"},
             {"Gfg" : "", "is" : "better", "best" : "8"},
             {"Gfg" : "9", "is" : "CS", "best" : "10"}]

# printing original list
print("The original list : " + str(test_list))

# initializing K key 
K = "Gfg"

# filter() used to iteration
# lambda for functionality
res = list(filter(lambda sub: sub[K] == '', test_list))

# printing result 
print("The extracted dictionaries : " + str(res))
```

**Output**

```py
The original list : [{'Gfg': '4', 'is': 'good', 'best': '1'}, {'Gfg': '', 'is': 'better', 'best': '8'}, {'Gfg': '9', 'is': 'CS', 'best': '10'}]
The extracted dictionaries : [{'Gfg': '', 'is': 'better', 'best': '8'}]

```