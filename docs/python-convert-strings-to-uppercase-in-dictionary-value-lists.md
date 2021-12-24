# Python–在字典值列表中将字符串转换为大写

> 原文:[https://www . geesforgeks . org/python-convert-string-to-大写-in-dictionary-value-list/](https://www.geeksforgeeks.org/python-convert-strings-to-uppercase-in-dictionary-value-lists/)

给定带有值列表的字典，将所有字符串转换为大写。

> **输入**:{“Gfg”:[“AB”、“CD”]、“Best”:[“GH”]、“is”:[“KL”]}
> **输出**:{“Gfg”:[“AB”、“CD”]、“Best”:[“GH”]、“is”:[“KL”]}
> **说明:**所有值列表字符串均转换为大写。
> 
> **输入**:{“Gfg”:[“AB”、“cd”、“Ef”]}
> **输出**:{“Gfg”:[“AB”、“CD”、“Ef”]}
> **解释**:所有值列表字符串都转换为大写，已经大写没有效果了。

**方法一:使用词典理解+上()+列表理解**

上述功能的组合可以用来解决这个问题。在这种情况下，我们使用大写()执行大写，使用列表理解来遍历所有字符串，使用字典理解来用大写值重新构建字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert Strings to Uppercase in Dictionary value lists
# Using dictionary comprehension + upper() + list comprehension

# initializing dictionary
test_dict = {"Gfg" : ["ab", "cd", "ef"],
             "Best" : ["gh", "ij"], "is" : ["kl"]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using upper to convert to upper case 
res = {key: [ele.upper() for ele in test_dict[key] ] for key in test_dict }

# printing result 
print("The dictionary after conversion " + str(res)) 
```

**Output**

> 原词典为:{'Gfg': ['ab '，' cd '，' ef']，' Best': ['gh '，' ij']，' is': ['kl']}
> 转换后的词典{'Gfg': ['AB '，' CD '，' EF']，' Best': ['GH '，' ij '，' is': ['kl']}

**方法二:使用 map() + upper() +词典理解**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 map()代替列表理解来执行扩展大写逻辑的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert Strings to Uppercase in Dictionary value lists
# Using map() + upper() + dictionary comprehension

# initializing dictionary
test_dict = {"Gfg" : ["ab", "cd", "ef"],
             "Best" : ["gh", "ij"], "is" : ["kl"]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# using map() to extend logic to all inner list 
res = {key: list(map(str.upper, test_dict[key])) for key in test_dict}

# printing result 
print("The dictionary after conversion " + str(res)) 
```

**Output**

> 原词典为:{'Gfg': ['ab '，' cd '，' ef']，' Best': ['gh '，' ij']，' is': ['kl']}
> 转换后的词典{'Gfg': ['AB '，' CD '，' EF']，' Best': ['GH '，' ij '，' is': ['kl']}