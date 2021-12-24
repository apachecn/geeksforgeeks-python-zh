# Python–过滤索引相似值

> 原文:[https://www . geesforgeks . org/python-filter-index-相似-values/](https://www.geeksforgeeks.org/python-filter-index-similar-values/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要从字典中的某个键匹配列表中的值中提取值列表中与筛选索引匹配的所有值。这种应用可以出现在 web 开发中。

> **输入**:test _ dict = {“Gfg”:[4，5，7]，“is”:[5，6，8]，“best”:[10，7，4]}
> **输出**:{“Gfg”:[4，5，7]，“is”:[5，6，8]，“best”:[10，7，4]}
> 
> **输入**:test _ dict = {“Gfg”:[4，20，5，7]，“is”:[5，17，6，8]，“best”:[10，11，7，4]}
> **输出**:{“Gfg”:[4，5，7]，“is”:[5，6，8]，“best”:[10，7，4]}

**方法#1:使用 loop + `zip() + defaultdict()`**
以上方法的组合可以用来解决这个问题。在这种情况下，我们用 list 初始化 defaultdict，用 zip()绑定所有键，并使用 loop 追加所需的元素。

```
# Python3 code to demonstrate working of 
# Filter index similar values
# Using loop + zip() + defaultdict()
from collections import defaultdict

# initializing dictionary
test_dict = {"Gfg" : [1, 4, 5, 6, 7], "is" : [5, 6, 8, 9, 10], 
                                 "best" : [10, 7, 4, 11, 23]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing value list 
filt_list = [4, 5, 7]

# Filter index similar values
# Using loop + zip() + defaultdict()
res = defaultdict(list)

for x, y, z in zip(test_dict['Gfg'], test_dict['is'], test_dict['best']):
    if x in filt_list:
        res['Gfg'].append(x)
        res['is'].append(y)
        res['best'].append(z)

# printing result 
print("The filtered dictionary : " + str(dict(res))) 
```

**Output :**

> 原始字典:{'Gfg': [1，4，5，6，7]，' is': [5，6，8，9，10]，' best': [10，7，4，11，23]}
> 过滤字典:{'Gfg': [4，5，7]，' is': [6，8，10]，' best': [7，4，23]}

**方法 2:使用列表理解+词典理解**
以上功能的组合可以用来解决这个问题。在这种情况下，我们使用列表理解提取索引，并使用字典理解从其他关键字中进行过滤。

```
# Python3 code to demonstrate working of 
# Filter index similar values
# Using list comprehension + dictionary comprehension

# initializing dictionary
test_dict = {"Gfg" : [1, 4, 5, 6, 7], "is" : [5, 6, 8, 9, 10], 
                                 "best" : [10, 7, 4, 11, 23]}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# initializing value list 
filt_list = [4, 5, 7]

# Filter index similar values
# Using list comprehension + dictionary comprehension
temp = [test_dict['Gfg'].index(idx) for idx in filt_list]
res = {key : [test_dict[key][idx] for idx in temp] for key in test_dict.keys()}

# printing result 
print("The filtered dictionary : " + str(res)) 
```

**Output :**

> 原始字典:{'Gfg': [1，4，5，6，7]，' is': [5，6，8，9，10]，' best': [10，7，4，11，23]}
> 过滤字典:{'Gfg': [4，5，7]，' is': [6，8，10]，' best': [7，4，23]}