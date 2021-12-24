# Python–检测字典中的循环

> 原文:[https://www . geesforgeks . org/python-detect-loop-in-dictionary/](https://www.geeksforgeeks.org/python-detect-loop-in-dictionaries/)

有时候，在使用 Python 字典时，我们可能会遇到这样的问题:当字典的值通过其他字典的键进行映射时，我们需要检查它们是否没有形成循环。这种问题可以应用于许多领域，包括竞争性编程和暴力。

> **输入** : test_dict1 = {9 : [1，5]，8 : [1，4]，10 : [4，2]}
> test_dict2 = {2 : [1，8]}
> **输出**:真
> 
> **输入** : test_dict1 = {15 : [1，5]}
> test_dict2 = {2 : [1，10]}
> **输出**:假

**方法#1:使用循环**
这是一种可以执行该任务的暴力方式。在这种情况下，我们迭代特定字典键的所有值，并用字典键中相似键的值进行映射。

```
# Python3 code to demonstrate working of 
# Detect loop in Dictionaries
# Using loop

# initializing dictionaries
test_dict1 = {7 : [1, 2], 8 : [1, 4], 9 : [4, 2]} 
test_dict2 = {2 : [1, 7], 10 : [1, 6], 11 : [24, 20]} 

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# Detect loop in Dictionaries
# Using loop
res = False
for idx1 in test_dict1.values():
    temp1 = (idx for idx in idx1 if idx in test_dict2)
    for idx in temp1:
        for idx2 in test_dict2[idx]:
            if idx2 in test_dict1:
                res = True

# printing result 
print("Does dictionaries contain loop : " + str(res)) 
```

**Output :**

```
The original dictionary 1 is : {8: [1, 4], 9: [4, 2], 7: [1, 2]}
The original dictionary 2 is : {2: [1, 7], 11: [24, 20], 10: [1, 6]}
Does dictionaries contain loop : True

```

**方法 2:使用`any()` +循环**
这是解决这个问题的简写。在这种情况下，我们通过灌输 any()来减少内部循环，如果存在任何循环，则返回 True。

```
# Python3 code to demonstrate working of 
# Detect loop in Dictionaries
# Using any() + loop

# initializing dictionaries
test_dict1 = {7 : [1, 2], 8 : [1, 4], 9 : [4, 2]} 
test_dict2 = {2 : [1, 7], 10 : [1, 6], 11 : [24, 20]} 

# printing original dictionaries
print("The original dictionary 1 is : " + str(test_dict1))
print("The original dictionary 2 is : " + str(test_dict2))

# Detect loop in Dictionaries
# Using any() + loop
res = False
for key, val in test_dict1.items():
    if any([vl in test_dict2 and key in test_dict2[vl] for vl in val]):
        res = True

# printing result 
print("Does dictionaries contain loop : " + str(res)) 
```

**Output :**

```
The original dictionary 1 is : {8: [1, 4], 9: [4, 2], 7: [1, 2]}
The original dictionary 2 is : {2: [1, 7], 11: [24, 20], 10: [1, 6]}
Does dictionaries contain loop : True

```