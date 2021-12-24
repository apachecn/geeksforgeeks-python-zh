# Python–K 列表嵌套字典网格

> 原文:[https://www . geesforgeks . org/python-k-list-nested-dictionary-mesh/](https://www.geeksforgeeks.org/python-k-list-nested-dictionary-mesh/)

给定两个列表，用常量列表创建嵌套网格。

> **输入** : test_list1 = [4，6]，test_list2 = [2，7]，K = []
> **输出** : {4: {2: []，7: []}，6: {2: []，7:[]}
> **解释**:用[]初始化的嵌套字典。
> 
> **输入** : test_list1 = [4]，test_list2 = [2]，K = [1]
> **输出**:{ 4:{ 2:[1]}
> **解释**:嵌套字典初始化为[1]。

**方法:使用词典理解**

在这种情况下，我们使用嵌套字典理解，列表 2 元素的内部元素作为键分配给列表 1 的每个元素，外部元素分配来自列表 1 的键。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# K list Nested Dictionary Mesh
# Using * operator

# initializing lists
test_list1 = [4, 6, 8, 7]
test_list2 = [2, 7, 9, 4]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# initializing K 
K = [None]

# initializing K list mesh
res = {idx: {sub2: K for sub2 in test_list2} for idx in test_list1}

# printing result 
print("Created Mesh : " + str(res))
```

**Output**

```
The original list 1 : [4, 6, 8, 7]
The original list 2 : [2, 7, 9, 4]
Created Mesh : {4: {2: [None], 7: [None], 9: [None], 4: [None]}, 6: {2: [None], 7: [None], 9: [None], 4: [None]}, 8: {2: [None], 7: [None], 9: [None], 4: [None]}, 7: {2: [None], 7: [None], 9: [None], 4: [None]}}

```