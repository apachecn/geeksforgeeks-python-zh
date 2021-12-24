# Python–从字典值列表中提取第 Kth 个索引元素

> 原文:[https://www . geesforgeks . org/python-extract-kth-index-elements-from-dictionary-value-list/](https://www.geeksforgeeks.org/python-extract-kth-index-elements-from-dictionary-value-list/)

给定一个以列表为值的字典，提取所有的 Kth 索引元素。

> **输入**:{“Gfg”:[4，7，5]，“Best”:[8，6，7]，“is”:[9，3，8]}，K = 2
> **输出** : [5，7，8]
> **解释**:第 2 个索引元素在不同的键中分别为 5，7，8。
> 
> **输入**:{“Gfg”:[4，7，5]，“Best”:[8，6，7]，“is”:[9，3，8]}，K = 0
> **输出** : [4，8，9]
> **解释**:第 0 个索引元素在不同的键中分别为 4，8，9。

**方法#1:使用列表理解+值()**

上述功能的组合可以用来解决这个问题。在这种情况下，使用 values()提取值，并使用列表理解来构建新列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract Kth index elements from Dictionary Value list
# Using list comprehension + values()

# initializing dictionary
test_dict = {"Gfg" : [4, 7, 5], "Best" : [8, 6, 7], "is" : [9, 3, 8]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 1

# one liner, values() getting all value according to keys
res = [sub[K] for sub in test_dict.values()]

# printing result 
print("The extracted values : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': [4, 7, 5], 'Best': [8, 6, 7], 'is': [9, 3, 8]}
The extracted values : [7, 6, 3]

```

**方法 2:使用 map() + itemgetter()**

上述功能的组合可以用来解决这个问题。在本文中，我们使用 map()来扩展获取特定键的值的逻辑，itemgetter 用于提取特定的索引。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Extract Kth index elements from Dictionary Value list
# Using map() + itemgetter()
from operator import itemgetter

# initializing dictionary
test_dict = {"Gfg" : [4, 7, 5], "Best" : [8, 6, 7], "is" : [9, 3, 8]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing K 
K = 1

# map and itemgetter() extracting result 
# list() used to convert result from map() to list format
res = list(map(itemgetter(K), test_dict.values()))

# printing result 
print("The extracted values : " + str(res)) 
```

**Output**

```
The original dictionary is : {'Gfg': [4, 7, 5], 'Best': [8, 6, 7], 'is': [9, 3, 8]}
The extracted values : [7, 6, 3]

```