# Python–字符串列表中的字符索引映射

> 原文:[https://www . geesforgeks . org/python-字符-索引-字符串映射-列表/](https://www.geeksforgeeks.org/python-character-indices-mapping-in-string-list/)

给定一个字符串列表，将字符串中的每个字符映射到它出现的索引。

> **输入** : test_list = ['g f g '，' b e s t '，' f o r '，' g e k s ']
> **输出** : {'g': [1，4]，' f': [1，3]，' s': [2，4]，' b': [2]，' e': [2，4]，' t': [2]，' o': [3]，' r': [3]，' k': [4]}
> **解释**:
> 
> **输入** : test_list = ['g f g '，' i s '，' b e s t '，' f o r '，' g e k s ']
> **输出** : {'g': [1，5]，' f': [1，4]，' i': [2]，' s': [2，3，5]，' e': [3，5]，' t': [3]，' o': [4]，' r': [4]，' k': [5]

**方法#1:使用 default dict()+enumerate()+split()**

上述功能的组合可以用来解决这个问题。在本例中，我们使用 defaultdict()获取空列表来存储索引，enumerate()用于检查索引，split()可用于拆分字符。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Charatacter indices Mapping in String List
# Using defaultdict() + enumerate() + split()
from collections import defaultdict

# initializing list
test_list = ['g f g', 'i s', 'b e s t', 'f o r', 'g e e k s'] 

# printing original list
print("The original list is : " + str(test_list))

res = defaultdict(set)

# loop for assigning indices
for idx, ele in enumerate(test_list):
    for sub in ele.split():
        res[sub].add(idx + 1)

# dictionary comprehension to remake result 
res = {key: list(val) for key, val in res.items()}

# printing result 
print("The mapped dictionary : " + str(res))
```

**Output**

```py
The original list is : ['g f g', 'i s', 'b e s t', 'f o r', 'g e e k s']
The mapped dictionary : {'g': [1, 5], 'f': [1, 4], 'i': [2], 's': [2, 3, 5], 'b': [3], 'e': [3, 5], 't': [3], 'o': [4], 'r': [4], 'k': [5]}

```

**方法 2:使用 enumerate() +词典理解**

这是执行该任务的另一种方式。这以类似的方式执行任务，只是在字典理解中以一种线性的方式。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Charatacter indices Mapping in String List
# Using enumerate() + dictionary comprehension

# initializing list
test_list = ['g f g', 'i s', 'b e s t', 'f o r', 'g e e k s'] 

# printing original list
print("The original list is : " + str(test_list))

# using dictionary comprehension to bind result
res = {sub : [key + 1 for key, val in enumerate(test_list) if sub in val] 
       for ele in test_list for sub in ele.split()}

# printing result 
print("The mapped dictionary : " + str(res))
```

**Output**

```py
The original list is : ['g f g', 'i s', 'b e s t', 'f o r', 'g e e k s']
The mapped dictionary : {'g': [1, 5], 'f': [1, 4], 'i': [2], 's': [2, 3, 5], 'b': [3], 'e': [3, 5], 't': [3], 'o': [4], 'r': [4], 'k': [5]}

```