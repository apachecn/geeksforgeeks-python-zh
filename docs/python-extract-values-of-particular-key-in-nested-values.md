# Python–提取嵌套值中特定键的值

> 原文:[https://www . geeksforgeeks . org/python-提取嵌套值中特定键的值/](https://www.geeksforgeeks.org/python-extract-values-of-particular-key-in-nested-values/)

给定一个以嵌套字典为值的字典，用特定的键提取所有的值。

> **输入**:test _ dict = { ' Gfg ':{“a”:7，“b”:9，“c”:12 }、“is”:{“a”:15，“b”:19，“c”:20 }、“best”:{“a”:5，“b”:10，“c”:2 } }、temp =“b”
> **输出**:【9、10、19】
> **:提取“b”键的所有值。**
> 
> ****输入**:test _ dict = { ' Gfg ':{“a”:7，“b”:9，“c”:12 }，“is”:{“a”:15，“b”:19，“c”:20 }，“best”:{“a”:5，“b”:10，“c”:2 } }，temp =“a”
> **输出**:【7，15，5】
> **解释:**提取“a”键的所有值。**

****方法#1:使用列表理解+项目()****

**这是执行这项任务的方法之一。在这种情况下，我们使用列表理解来执行提取特定关键字的任务，并使用 items()来获取所有项()。**

## **蟒蛇 3**

```py
# Python3 code to demonstrate working of 
# Extract values of Particular Key in Nested Values
# Using list comprehension

# initializing dictionary
test_dict = {'Gfg' : {"a" : 7, "b" : 9, "c" : 12},
             'is' : {"a" : 15, "b" : 19, "c" : 20}, 
             'best' :{"a" : 5, "b" : 10, "c" : 2}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing key
temp = "c"

# using item() to extract key value pair as whole
res = [val[temp] for key, val in test_dict.items() if temp in val]

# printing result 
print("The extracted values : " + str(res)) 
```

****Output**

```py
The original dictionary is : {'Gfg': {'a': 7, 'b': 9, 'c': 12}, 'is': {'a': 15, 'b': 19, 'c': 20}, 'best': {'a': 5, 'b': 10, 'c': 2}}
The extracted values : [12, 20, 2]

```** 

****方法 2:使用列表理解+值()+键()****

**上述功能的组合可以用来解决这个问题。在本文中，我们使用 values()和 key()分别获取值和键，而不是使用 items()一次提取。**

## **蟒蛇 3**

```py
# Python3 code to demonstrate working of 
# Extract values of Particular Key in Nested Values
# Using list comprehension + values() + keys() 

# initializing dictionary
test_dict = {'Gfg' : {"a" : 7, "b" : 9, "c" : 12},
             'is' : {"a" : 15, "b" : 19, "c" : 20}, 
             'best' :{"a" : 5, "b" : 10, "c" : 2}}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing key
temp = "c"

# using keys() and values() to extract values
res = [sub[temp] for sub in test_dict.values() if temp in sub.keys()]

# printing result 
print("The extracted values : " + str(res)) 
```

****Output**

```py
The original dictionary is : {'Gfg': {'a': 7, 'b': 9, 'c': 12}, 'is': {'a': 15, 'b': 19, 'c': 20}, 'best': {'a': 5, 'b': 10, 'c': 2}}
The extracted values : [12, 20, 2]

```**