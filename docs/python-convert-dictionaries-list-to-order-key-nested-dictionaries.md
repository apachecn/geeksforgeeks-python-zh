# Python–将字典列表转换为顺序键嵌套字典

> 原文:[https://www . geesforgeks . org/python-convert-dictionary-list-to-order-key-nested-dictionary/](https://www.geeksforgeeks.org/python-convert-dictionaries-list-to-order-key-nested-dictionaries/)

给定字典列表，转换为有序关键字字典，每个关键字包含字典作为其嵌套值。

> **输入**:test _ List =[{“Gfg”:3，4 : 9}，{“is”:8，“Good”:2 }]
> **输出**:{ 0:{“Gfg”:3，4: 9}，1:{“is”:8，“Good”:2 } }
> **解释**:列表转换为带索引键的字典。
> 
> **输入**:test _ List =[{“is”:8，“Good”:2 }]
> **输出**:{ 1:{“is”:8，“Good”:2 } }
> **解释** : List 转换成带索引键的字典，就一行。

**方法#1:使用循环+枚举()**

这是执行这项任务的粗暴方式。在这种情况下，我们使用枚举和创建自定义必需字典一起遍历索引和值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert Dictionaries List to Order Key Nested dictionaries
# Using loop + enumerate()

# initializing lists
test_list = [{"Gfg" : 3, 4 : 9}, {"is": 8, "Good" : 2}, {"Best": 10, "CS" : 1}]

# printing original list
print("The original list : " + str(test_list))

# using enumerate() to extract key to map with dict values 
res = dict()
for idx, val in enumerate(test_list):
    res[idx] = val

# printing result 
print("The constructed dictionary : " + str(res))
```

**Output**

```
The original list : [{'Gfg': 3, 4: 9}, {'is': 8, 'Good': 2}, {'Best': 10, 'CS': 1}]
The constructed dictionary : {0: {'Gfg': 3, 4: 9}, 1: {'is': 8, 'Good': 2}, 2: {'Best': 10, 'CS': 1}}

```

**方法 2:使用词典理解+枚举()**

这类似于上面的方法，唯一的区别是使用字典理解代替循环来执行封装任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert Dictionaries List to Order Key Nested dictionaries
# Using dictionary comprehension + enumerate() 

# initializing lists
test_list = [{"Gfg" : 3, 4 : 9}, {"is": 8, "Good" : 2}, {"Best": 10, "CS" : 1}]

# printing original list
print("The original list : " + str(test_list))

# dictionary comprehension encapsulating result as one liner
res = {idx : val for idx, val in enumerate(test_list)}

# printing result 
print("The constructed dictionary : " + str(res))
```

**Output**

```
The original list : [{'Gfg': 3, 4: 9}, {'is': 8, 'Good': 2}, {'Best': 10, 'CS': 1}]
The constructed dictionary : {0: {'Gfg': 3, 4: 9}, 1: {'is': 8, 'Good': 2}, 2: {'Best': 10, 'CS': 1}}

```