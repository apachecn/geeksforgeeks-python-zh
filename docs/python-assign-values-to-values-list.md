# Python–为值列表赋值

> 原文:[https://www . geesforgeks . org/python-赋值给值-列表/](https://www.geeksforgeeks.org/python-assign-values-to-values-list/)

给定 2 个字典，给字典 2 中的值列表元素赋值。

> **输入** : test_dict = {'Gfg' : [3，6]，' best' :[9]}，look_dict = {3 : [1，5]，6 : "Best "，9 : 12}
> **输出** : {'Gfg': {3: [1，5]，6: 'Best'}，' best': {9: 12}}
> **解释** : 3 替换为键 3 和值[1，5]等等。
> 
> **输入** : test_dict = {'Gfg' : [3，6]}，look_dict = {3 : [1，5]，6:【最佳】}
> **输出** : {'Gfg': {3: [1，5]，6:'最佳' }}
> **解释** : 3 替换为键 3 和值[1，5]等等。

**方法一:使用嵌套词典理解**

在这种情况下，我们使用内部字典理解将值元素映射到 dict 2，外部 dict 用于从字典 1 中提取所有键。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Assign values to Values List
# Using nested dictionary comprehension

# initializing dictionary
test_dict = {'Gfg' : [3, 6],
             'is' : [4, 2], 
             'best' :[9]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing lookup dict 
look_dict = {3 : [1, 5], 6 : "Best", 4 : 10, 9 : 12, 2 : "CS"}

# nested dictionaries to sought solution
res = {idx: {ikey: look_dict[ikey] for ikey in test_dict[idx]} for idx in test_dict}

# printing result 
print("The mapped dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': [3, 6], 'is': [4, 2], 'best': [9]}
The mapped dictionary : {'Gfg': {3: [1, 5], 6: 'Best'}, 'is': {4: 10, 2: 'CS'}, 'best': {9: 12}}

```

**方法二:使用物品()+字典理解**

与上述方法类似，另一个是单行的，区别在于 items()用于元素访问。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Assign values to Values List
# Using items() + dictionary comprehension

# initializing dictionary
test_dict = {'Gfg': [3, 6],
             'is': [4, 2],
             'best': [9]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# initializing lookup dict
look_dict = {3: [1, 5], 6: "Best", 4: 10, 9: 12, 2: "CS"}

# nested dictionaries to sought solution
# items() used to access key-val pairs
res = {key: {ikey: ival for (ikey, ival) in look_dict.items(
) if ikey in val} for (key, val) in test_dict.items()}

# printing result
print("The mapped dictionary : " + str(res))
```

**Output**

```py
The original dictionary is : {'Gfg': [3, 6], 'is': [4, 2], 'best': [9]}
The mapped dictionary : {'Gfg': {3: [1, 5], 6: 'Best'}, 'is': {4: 10, 2: 'CS'}, 'best': {9: 12}}

```