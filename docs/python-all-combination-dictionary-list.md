# Python–全组合字典列表

> 原文:[https://www . geesforgeks . org/python-all-combination-dictionary-list/](https://www.geeksforgeeks.org/python-all-combination-dictionary-list/)

给定两个列表，形成所有可能的字典组合，这些字典可以通过从列表 1 中取关键字和从列表 2 中取值来形成。

> **输入**:test _ list 1 =[“Gfg”、“is”、“Best”]，test_list2 = [4]
> **输出**:[{“Gfg”:4、“is”:4、“Best”:4 }]
> **解释**:所有组合字典列表提取。
> 
> **输入**:test _ list 1 =[“Gfg”，“is”，“Best”]，test_list2 = [5，6]
> **输出**:[{“Gfg”:5，“is”:5，“Best”:5 }，{“Gfg”:5，“is”:5，“Best”:6 }，{“Gfg”:5，“is”:6，“Best”:5 }，{“Gfg”:5，“is”:6，“Best”:6 }，{“Gfg”:6，“is”:5，“Best”:5 }，{”

**方法一:使用积()+词典理解+列表理解**

在这种情况下，我们使用 product()获得所有可能的组合，字典理解生成每个字典，列表理解用于迭代生成的组合。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# All combination Dictionary List
# Using product() + list comprehension + dictionary comprehension
from itertools import product

# initializing lists
test_list1 = ["Gfg", "is", "Best"]
test_list2 = [4, 5]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# generating combinations
temp = product(test_list2, repeat = len(test_list1))

# constructing dicts using combinations
res = [{key : val for (key , val) in zip(test_list1, ele)} for ele in temp]

# printing result 
print("The combinations dictionary : " + str(res))
```

**输出:**

> 原始列表 1 是:['Gfg '，' is '，' Best']
> 原始列表 2 是:【4，5】
> 组合字典:[{'Gfg': 4，' is': 4，' Best': 4}，{'Gfg': 4，' is': 5，' Best': 4}，{'Gfg': 4，' is': 5，' Best': 5}，{'Gfg': 5，' is': 4，' Best': 4}，{'Gfg': 5，' is ':是':

**方法 2:使用排列()+词典理解+列表理解【针对独特元素】**

如果我们要求值都是唯一的，置换()可以代替乘积()来完成这个任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# All combination Dictionary List
# Using product() + list comprehension + dictionary comprehension
from itertools import permutations

# initializing lists
test_list1 = ["Gfg", "is", "Best"]
test_list2 = [4, 5, 6]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# generating combinations
temp = list(permutations(test_list2, len(test_list1)))

# constructing dicts using combinations
res = [{key: val for (key, val) in zip(test_list1, ele)} for ele in temp]

# printing result
print("The combinations dictionary : " + str(res))
```

**输出:**

> 原列表 1 为:['Gfg '，' is '，' Best']
> 原列表 2 为:【4，5，6】
> 组合词典:[{'Gfg': 4，' is': 5，' Best': 6}，{'Gfg': 4，' is': 6 '，{'Gfg': 5，' is': 4，' Best': 6}，{'Gfg': 5，' is': 6，' Best': 4}，{'Gfg': 6，' is': 4，' Best': 5}，{'Gfg': 6 ' '