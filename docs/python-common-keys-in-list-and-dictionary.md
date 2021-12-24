# Python–列表和字典中的常用键

> 原文:[https://www . geesforgeks . org/python-列表和字典中的常用键/](https://www.geeksforgeeks.org/python-common-keys-in-list-and-dictionary/)

给定一个字典和列表，提取所有常用的关键字和列表。

> **输入**:test _ dict = {“Gfg”:3、“is”:5、“best”:9、“for”:0、“极客”:3}、test _ list =[“Gfg”、“best”、“CS”]
> **输出**:[‘Gfg’、‘best’]
> **解释** : Gfg 和 best 都出现在字典和 List 中。
> 
> **输入**:test _ dict = {“Gfg”:3、“is”:5、“best”:9、“for”:0、“极客”:3}、test _ list =[“Gfg”、“good”、“CS”]
> **输出**:[‘Gfg’]
> **解释** : Gfg 在字典和 List 中都存在。

**方法一:使用列表理解**

这是执行这项任务的方法之一。在这种情况下，我们迭代所有的字典和列表值，如果找到匹配的，它们被添加到结果中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Common keys in list and dictionary
# Using list comprehension

# initializing dictionary
test_dict = {"Gfg": 3, "is" : 5, "best" : 9, "for" : 0, "geeks" : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing test_list 
test_list = ["Gfg", "best", "geeks"]

# using in operator to check for match 
res = [ele for ele in test_dict if ele in test_list]

# printing result 
print("The required result : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 3, 'is': 5, 'best': 9, 'for': 0, 'geeks': 3}
The required result : ['Gfg', 'best', 'geeks']

```

**方法 2:使用 set() +交集()**

这是执行这项任务的另一种方式。在这种情况下，我们将容器、列表和字典键转换为 set()，然后相交以找到所需的匹配。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Common keys in list and dictionary
# Using set() + intersection()

# initializing dictionary
test_dict = {"Gfg": 3, "is" : 5, "best" : 9, "for" : 0, "geeks" : 3}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing test_list 
test_list = ["Gfg", "best", "geeks"]

# intersection() used to get Common elements 
res = set(test_list).intersection(set(test_dict))

# printing result 
print("The required result : " + str(list(res))) 
```

**Output**

```py
The original dictionary is : {'Gfg': 3, 'is': 5, 'best': 9, 'for': 0, 'geeks': 3}
The required result : ['best', 'geeks', 'Gfg']

```