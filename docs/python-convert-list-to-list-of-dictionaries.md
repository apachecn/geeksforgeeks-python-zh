# Python–将列表转换为词典列表

> 原文:[https://www . geesforgeks . org/python-convert-list-to-list-of-dictionary/](https://www.geeksforgeeks.org/python-convert-list-to-list-of-dictionaries/)

给定列表值和键值列表，以字典列表的形式将这些值转换为键值对。

> **输入** : test_list = ["Gfg "，3，" is "，8]，key_list = ["name "，" id"]
> **输出** : [{'name': 'Gfg '，' id': 3}，{'name': 'is '，' id': 8}]
> **解释**:自定义键映射的值，【name】->“Gfg”，“id”->3。
> 
> **输入** : test_list = ["Gfg "，10]，key_list = ["name "，" id"]
> **输出** : [{'name': 'Gfg '，' id': 10}]
> **解释**:通过按键映射将列表转换为记录列表。

**方法一:使用循环+词典理解**

这是执行这项任务的方法之一。在本文中，我们使用字典理解来执行映射值。使用循环执行迭代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert List to List of dictionaries
# Using dictionary comprehension + loop

# initializing lists
test_list = ["Gfg", 3, "is", 8, "Best", 10, "for", 18, "Geeks", 33]

# printing original list
print("The original list : " + str(test_list))

# initializing key list 
key_list = ["name", "number"]

# loop to iterate through elements
# using dictionary comprehension
# for dictionary construction
n = len(test_list)
res = []
for idx in range(0, n, 2):
    res.append({key_list[0]: test_list[idx], key_list[1] : test_list[idx + 1]})

# printing result 
print("The constructed dictionary list : " + str(res))
```

**Output**

> 原始列表:['Gfg '，3，' is '，8，' Best '，10，' for '，18，' Geeks '，33]
> 构造的字典列表:[{'name': 'Gfg '，' number': 3}，{'name': 'is '，' number': 8}，{'name': 'Best '，' number': 10}，{'name': 'for '，' number': 18}，{'name': 'Geeks '，' number': 33}]

**方法二:使用词典理解+列表理解**

上述功能的组合用于解决这个问题。在这种情况下，我们执行与上述方法类似的任务。但不同的是，它是作为速记来执行的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert List to List of dictionaries
# Using zip() + list comprehension

# initializing lists
test_list = ["Gfg", 3, "is", 8, "Best", 10, "for", 18, "Geeks", 33]

# printing original list
print("The original list : " + str(test_list))

# initializing key list 
key_list = ["name", "number"]

# using list comprehension to perform as shorthand
n = len(test_list)
res = [{key_list[0]: test_list[idx], key_list[1]: test_list[idx + 1]}
       for idx in range(0, n, 2)]

# printing result 
print("The constructed dictionary list : " + str(res))
```

**Output**

> 原始列表:['Gfg '，3，' is '，8，' Best '，10，' for '，18，' Geeks '，33]
> 构造的字典列表:[{'name': 'Gfg '，' number': 3}，{'name': 'is '，' number': 8}，{'name': 'Best '，' number': 10}，{'name': 'for '，' number': 18}，{'name': 'Geeks '，' number': 33}]