# Python–两个字典值列表的交叉映射

> 原文:[https://www . geesforgeks . org/python-两个字典值列表的交叉映射/](https://www.geeksforgeeks.org/python-cross-mapping-of-two-dictionary-value-lists/)

给定两个具有列表值的字典，通过检查值-键链接，执行第一个列表的键与其他列表的值的映射。

> **输入**:test _ dict 1 = {“Gfg”:[4，10]，“Best”:[8，6]，“is”:[9，3]}，test_dict2 = {6 : [15，9]，8 : [6，3]，7 : [9，8]，9 : [10，11]}
> **输出**:{“Best”:[6，3，15，9]，“is”:[10，11]}
> **解释**:”
> 
> **输入**:test _ dict 1 = {“Gfg”:[4，10]，“Best”:[18，16]，“is”:[9，3]}，test_dict2 = {6 : [15，9]，8 : [6，3]，7 : [9，8]，9 : [10，11]}
> **输出** : {'is': [10，11]}
> **解释**:只有 9 作为可能的键存在。

**方法#1:使用循环+ setdefault() + extend()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用 get()执行获取具有值的匹配键的任务，并使用 setdefault 构造空列表进行映射。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Cross mapping of Two dictionary value lists
# Using loop + setdefault() + extend()

# initializing dictionaries
test_dict1 = {"Gfg" : [4, 7], "Best" : [8, 6], "is" : [9, 3]}
test_dict2 = {6 : [15, 9], 8 : [6, 3], 7 : [9, 8], 9 : [10, 11]}

# printing original lists
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

res = {}

# getting all values of first dictionary 
for key, val in test_dict1.items():
    for key1 in val:

        # getting result with default value list and extending 
        # according to value optained from get()
        res.setdefault(key, []).extend(test_dict2.get(key1, []))

# printing result 
print("The constructed dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary 1 is : {'Gfg': [4, 7], 'Best': [8, 6], 'is': [9, 3]}
The original dictionary 2 is : {6: [15, 9], 8: [6, 3], 7: [9, 8], 9: [10, 11]}
The constructed dictionary : {'Gfg': [9, 8], 'Best': [6, 3, 15, 9], 'is': [10, 11]}

```

**方法二:使用列表理解+词典理解**

这是解决这个问题的又一个方法。在这种情况下，我们使用列表理解提取所有映射，然后通过交叉映射提取的值来构建新的字典。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Cross mapping of Two dictionary value lists
# Using list comprehension + dictionary comprehension

# initializing dictionaries
test_dict1 = {"Gfg" : [4, 7], "Best" : [8, 6], "is" : [9, 3]}
test_dict2 = {6 : [15, 9], 8 : [6, 3], 7 : [9, 8], 9 : [10, 11]}

# printing original lists
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# using internal and external comprehension to 
# solve problem 
res = {key: [j for i in val if i in test_dict2 for j in test_dict2[i]]
      for key, val in test_dict1.items()}

# printing result 
print("The constructed dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary 1 is : {'Gfg': [4, 7], 'Best': [8, 6], 'is': [9, 3]}
The original dictionary 2 is : {6: [15, 9], 8: [6, 3], 7: [9, 8], 9: [10, 11]}
The constructed dictionary : {'Gfg': [9, 8], 'Best': [6, 3, 15, 9], 'is': [10, 11]}

```