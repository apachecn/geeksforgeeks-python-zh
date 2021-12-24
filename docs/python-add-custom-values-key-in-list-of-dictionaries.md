# Python–在字典列表中添加自定义键值

> 原文:[https://www . geesforgeks . org/python-add-custom-values-键入字典列表/](https://www.geeksforgeeks.org/python-add-custom-values-key-in-list-of-dictionaries/)

给定一个字典列表、自定义列表和关键字，将关键字按顺序添加到每个字典的列表值中。

> **输入**:test _ list =[{“Gfg”:6，“is”:9，“best”:10 }，{“Gfg”:8，“is”:11，“best”:19 }，{“Gfg”:2，“is”:16，“best”:10 }]，K =“Geeks”，追加 _list = [6，7，4]
> **输出**:[{“Gfg”:6，“is”:9，“best”:10，“Geeks”:6 }，{“Gfg”:8，“is”:10
> 
> **输入**:test _ list =[{“Gfg”:6，“is”:9，“best”:10 }]，K =“CS”，append_list = [6]
> **输出**:[{“Gfg”:6，“is”:9，“best”:10，“CS”:6 }]
> **解释**:“CS”键以 6 为值加入各字典。

**方法#1:使用循环+枚举()**

这是执行这项任务的方法之一。在这种情况下，我们使用 enumerate()遍历字典以获取索引，并不断为每个字典键分配其索引值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Add custom values key in List of dictionaries
# Using loop

# initializing lists
test_list = [{"Gfg" : 6, "is" : 9, "best" : 10}, 
             {"Gfg" : 8, "is" : 11, "best" : 19},
             {"Gfg" : 2, "is" : 16, "best" : 10},
             {"Gfg" : 12, "is" : 1, "best" : 8},
             {"Gfg" : 22, "is" : 6, "best" : 8}]

# printing original list
print("The original list : " + str(test_list))

# initializing Key 
K = "CS"

# initializing list 
append_list = [6, 7, 4, 3, 9]

# using enumerate() to iterate for index and values
for idx, ele in enumerate(test_list):
        ele[K] = append_list[idx]

# printing result 
print("The dictionary list after addition : " + str(test_list))
```

**Output**

```
The original list : [{'Gfg': 6, 'is': 9, 'best': 10}, {'Gfg': 8, 'is': 11, 'best': 19}, {'Gfg': 2, 'is': 16, 'best': 10}, {'Gfg': 12, 'is': 1, 'best': 8}, {'Gfg': 22, 'is': 6, 'best': 8}]
The dictionary list after addition : [{'Gfg': 6, 'is': 9, 'best': 10, 'CS': 6}, {'Gfg': 8, 'is': 11, 'best': 19, 'CS': 7}, {'Gfg': 2, 'is': 16, 'best': 10, 'CS': 4}, {'Gfg': 12, 'is': 1, 'best': 8, 'CS': 3}, {'Gfg': 22, 'is': 6, 'best': 8, 'CS': 9}]

```

**方法 2:使用 zip() + loop**

这是执行这项任务的另一种方式。在本文中，我们使用 zip()执行列表值与每个字典的映射。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Add custom values key in List of dictionaries
# Using zip() + loop

# initializing lists
test_list = [{"Gfg" : 6, "is" : 9, "best" : 10}, 
             {"Gfg" : 8, "is" : 11, "best" : 19},
             {"Gfg" : 2, "is" : 16, "best" : 10},
             {"Gfg" : 12, "is" : 1, "best" : 8},
             {"Gfg" : 22, "is" : 6, "best" : 8}]

# printing original list
print("The original list : " + str(test_list))

# initializing Key 
K = "CS"

# initializing list 
append_list = [6, 7, 4, 3, 9]

# zip() used to bind index wise 
# list and dictionary
for dic, lis in zip(test_list, append_list):
  dic[K] = lis

# printing result 
print("The dictionary list after addition : " + str(test_list))
```

**Output**

```
The original list : [{'Gfg': 6, 'is': 9, 'best': 10}, {'Gfg': 8, 'is': 11, 'best': 19}, {'Gfg': 2, 'is': 16, 'best': 10}, {'Gfg': 12, 'is': 1, 'best': 8}, {'Gfg': 22, 'is': 6, 'best': 8}]
The dictionary list after addition : [{'Gfg': 6, 'is': 9, 'best': 10, 'CS': 6}, {'Gfg': 8, 'is': 11, 'best': 19, 'CS': 7}, {'Gfg': 2, 'is': 16, 'best': 10, 'CS': 4}, {'Gfg': 12, 'is': 1, 'best': 8, 'CS': 3}, {'Gfg': 22, 'is': 6, 'best': 8, 'CS': 9}]

```