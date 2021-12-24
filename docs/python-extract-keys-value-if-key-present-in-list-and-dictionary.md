# Python–提取关键字的值，如果关键字出现在列表和字典中

> 原文:[https://www . geesforgeks . org/python-extract-key-value-if-key-present-in-list-and-dictionary/](https://www.geeksforgeeks.org/python-extract-keys-value-if-key-present-in-list-and-dictionary/)

给定一个列表、字典和一个密钥 K，如果密钥同时存在于列表和字典中，则打印字典中的 K 值。

> **输入**:test _ list =[“Gfg”，“is”，“Good”，“for”，“Geeks”]，test _ dict = {“Gfg”:5，“Best”:6 }，K =“Gfg”
> **输出** : 5
> **解释**:“Gfg”存在于列表中，在字典中有值 5。
> 
> **输入**:test _ list =[“Good”、“for”、“Geeks”]，test _ dict = {“Gfg”:5、“Best”:6 }、K =“Gfg”
> **输出**:无
> **解释**:“Gfg”不在 List 中。

**方法#1:使用 all() +生成器表达式**

上述功能的结合提供了解决这个问题的方法之一。在本文中，我们使用 all()来检查字典和列表中的出现。如果结果为真，则将值提取到结果中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract Key's Value, if Key Present in List and Dictionary
# Using all() + list comprehension

# initializing list
test_list = ["Gfg", "is", "Good", "for", "Geeks"]

# initializing Dictionary
test_dict = {"Gfg" : 2, "is" : 4, "Best" : 6}

# initializing K 
K = "Gfg"

# printing original list and Dictionary
print("The original list : " + str(test_list))
print("The original Dictionary : " + str(test_dict))

# using all() to check for occurrence in list and dict
# encapsulating list and dictionary keys in list 
res = None 
if all(K in sub for sub in [test_dict, test_list]):
    res = test_dict[K]

# printing result 
print("Extracted Value : " + str(res))
```

**Output**

```py
The original list : ['Gfg', 'is', 'Good', 'for', 'Geeks']
The original Dictionary : {'Gfg': 2, 'is': 4, 'Best': 6}
Extracted Value : 2

```

**方法 2:使用 set() +交集()**

这是检查两个容器中是否有钥匙的另一种方法。在本文中，我们计算列表和字典键的所有值的交集，并测试键在其中的出现。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract Key's Value, if Key Present in List and Dictionary
# Using set() + intersection()

# initializing list
test_list = ["Gfg", "is", "Good", "for", "Geeks"]

# initializing Dictionary
test_dict = {"Gfg" : 2, "is" : 4, "Best" : 6}

# initializing K 
K = "Gfg"

# printing original list and Dictionary
print("The original list : " + str(test_list))
print("The original Dictionary : " + str(test_dict))

# conversion of lists to set and intersection with keys 
# using intersection
res = None 
if K in set(test_list).intersection(test_dict):
    res = test_dict[K]

# printing result 
print("Extracted Value : " + str(res))
```

**Output**

```py
The original list : ['Gfg', 'is', 'Good', 'for', 'Geeks']
The original Dictionary : {'Gfg': 2, 'is': 4, 'Best': 6}
Extracted Value : 2

```