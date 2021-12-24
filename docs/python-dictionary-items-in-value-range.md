# Python–值范围内的字典项目

> 原文:[https://www . geesforgeks . org/python-dictionary-items-in-value-range/](https://www.geeksforgeeks.org/python-dictionary-items-in-value-range/)

给定一个值范围，提取其关键字位于值范围内的所有项目。

> **输入** : {'Gfg' : 6，' is' : 7，' best' : 9，' for' : 8，'极客':11}，I，j = 9，12
> **输出** : {'best' : 9，'极客':11}
> **解释**:9 和 11 范围内的按键被提取。
> 
> **输入** : {'Gfg' : 6，' is' : 7，' best' : 9，' for' : 8，' geeks' : 11}，I，j = 14，18
> **输出** : {}
> **解释**:范围内无值。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，我们对所有键运行一个循环，并对值的范围进行条件检查。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dictionary items in value range
# Using loop

# initializing dictionary
test_dict = {'Gfg' : 6, 'is' : 7, 'best' : 9, 'for' : 8, 'geeks' : 11} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing range 
i, j = 8, 12

# using loop to iterate through all keys
res = dict()
for key, val in test_dict.items():
    if int(val) >= i and int(val) <= j:
        res[key] = val

# printing result 
print("The extracted dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 6, 'is': 7, 'best': 9, 'for': 8, 'geeks': 11}
The extracted dictionary : {'best': 9, 'for': 8, 'geeks': 11}

```

**方法 2:使用 filter() + lambda +字典理解**

上述功能的组合可以用来解决这个问题。在本例中，我们使用 filter()执行过滤任务，lambda 用于条件检查。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dictionary items in value range
# Using filter() + lambda + dictionary comprehension 

# initializing dictionary
test_dict = {'Gfg' : 6, 'is' : 7, 'best' : 9, 'for' : 8, 'geeks' : 11} 

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing range 
i, j = 8, 12

# using dictionary comprehension to compile result in one 
res = {key: val for key, val in filter(lambda sub: int(sub[1]) >= i and
                                   int(sub[1]) <= j, test_dict.items())}

# printing result 
print("The extracted dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 6, 'is': 7, 'best': 9, 'for': 8, 'geeks': 11}
The extracted dictionary : {'best': 9, 'for': 8, 'geeks': 11}

```