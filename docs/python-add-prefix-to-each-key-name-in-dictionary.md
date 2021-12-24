# Python–为字典中的每个键名添加前缀

> 原文:[https://www . geesforgeks . org/python-给每个关键字添加前缀-字典中的名称/](https://www.geeksforgeeks.org/python-add-prefix-to-each-key-name-in-dictionary/)

给定一个字典，通过给每个键添加前缀来更新它的每个键。

> **输入** : test_dict = {'Gfg' : 6，' is' : 7，' best' : 9}，temp = "Pro"
> **输出** : {'ProGfg' : 6，' Prois' : 7，' Probest' : 9}
> **解释**:“Pro”前缀添加到每个键。
> 
> **输入** : test_dict = {'Gfg' : 6，' is' : 7，' best' : 9}，temp = "a"
> **输出** : {'aGfg' : 6，' ais' : 7，' abest' : 9}
> **解释**:“a”前缀添加到每个键。

**方法一:利用词典理解**

这是可以执行此任务的方法之一。在这种情况下，我们通过对所有关键字执行前缀连接来构建新字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Add prefix to each key name in dictionary
# Using loop

# initializing dictionary
test_dict = {'Gfg' : 6, 'is' : 7, 'best' : 9, 'for' : 8, 'geeks' : 11} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing prefix 
temp = "Pro"

# + operator is used to perform task of concatenation
res = {temp + str(key): val for key, val in test_dict.items()}

# printing result 
print("The extracted dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 6, 'is': 7, 'best': 9, 'for': 8, 'geeks': 11}
The extracted dictionary : {'ProGfg': 6, 'Prois': 7, 'Probest': 9, 'Profor': 8, 'Progeeks': 11}

```

**方法 2:使用 f 字符串+词典理解**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 f 字符串执行串联任务。仅适用于> =3.6 版本的 Python。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Add prefix to each key name in dictionary
# Using f strings + dictionary comprehension

# initializing dictionary
test_dict = {'Gfg' : 6, 'is' : 7, 'best' : 9, 'for' : 8, 'geeks' : 11} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing prefix 
temp = "Pro"

# dictionary comprehension is used to bind result 
# f strings are used to bind prefix with key
res = {f"Pro{key}": val for key, val in test_dict.items()}

# printing result 
print("The extracted dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 6, 'is': 7, 'best': 9, 'for': 8, 'geeks': 11}
The extracted dictionary : {'ProGfg': 6, 'Prois': 7, 'Probest': 9, 'Profor': 8, 'Progeeks': 11}

```