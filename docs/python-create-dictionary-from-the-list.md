# Python–从列表中创建字典

> 原文:[https://www . geesforgeks . org/python-create-dictionary-from-list/](https://www.geeksforgeeks.org/python-create-dictionary-from-the-list/)

给定一个列表。任务是将其转换为字典，其中值作为列表元素，键作为给定字符串 K 和值的串联。

**示例:**

> **输入**:test _ list =[“gfg”，“is”，“best”]，K =“pref _”
> **输出** : {'pref_gfg': 'gfg '，' pref_is': 'is '，' pref_best': 'best'}
> **解释**:连接 K 后构造的键
> 
> **输入**:test _ list =[“gfg”、“best”]，K =“pref _”
> **输出**:{‘pref _ gfg’:‘gfg’，‘pref _ best’:‘best’}
> **解释**:串接 K 后构造的按键

**方法#1:使用循环**

这是执行这项任务的方法之一。在这种情况下，我们使用+运算符执行串联来构造键，并从列表中提取值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Values derived Dictionary keys
# Using loop

# initializing list
test_list = ["gfg", "is", "best"] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = "def_key_"

# using loop to construct new Dictionary
# + operator used to concat default key and values 
res = dict()
for ele in test_list:
    res[K + str(ele)] = ele 

# printing result 
print("The constructed Dictionary : " + str(res))
```

**输出:**

> 原始列表为:['gfg '，' is '，' best']
> 构造的字典:{'def_key_gfg': 'gfg '，' def_key_is': 'is '，' def_key_best': 'best'}

**方法二:使用** [**词典理解**](https://www.geeksforgeeks.org/python-dictionary-comprehension/)

这是执行这项任务的另一种方式。在这篇文章中，我们使用字典理解来构建一个使用一行的字典。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Values derived Dictionary keys
# Using dictionary comprehension

# initializing list
test_list = ["gfg", "is", "best"] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = "def_key_"

# using dictionary comprehension
# + operator used to concat default key and values 
res = {K + str(ele) : ele for ele in test_list}

# printing result 
print("The constructed Dictionary : " + str(res))
```

**输出:**

> 原始列表为:['gfg '，' is '，' best']
> 构造的字典:{'def_key_gfg': 'gfg '，' def_key_is': 'is '，' def_key_best': 'best'}