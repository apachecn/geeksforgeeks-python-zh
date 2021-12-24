# Python–使用给定列表创建嵌套字典

> 原文:[https://www . geesforgeks . org/python-create-nested-dictionary-use-给定-list/](https://www.geeksforgeeks.org/python-create-nested-dictionary-using-given-list/)

给定一个列表和字典，将列表的每个元素映射到字典的每个条目，形成嵌套字典作为值。

> **输入** : test_dict = {'Gfg' : 4，' best' : 9}，test_list = [8，2]
> **输出** : {8: {'Gfg': 4}，2: {'best': 9}}
> **解释**:从 list [8]到 dict {'Gfg' : 4}的索引式键值配对，以此类推。
> 
> **输入** : test_dict = {'Gfg' : 4}，test_list = [8]
> **输出** : {8: {'Gfg': 4}}
> **解释**:从 list [8]到 dict {'Gfg' : 4}的索引式键值配对。

**方法#1:使用 loop + zip()**

这是执行这项任务的方法之一。在这种情况下，我们使用 zip()组合这两个列表，并使用 loop 进行压缩键和字典构造的迭代。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Nested Dictionary with List
# Using loop + zip()

# initializing dictionary and list
test_dict = {'Gfg' : 4, 'is' : 5, 'best' : 9} 
test_list = [8, 3, 2]

# printing original dictionary and list
print("The original dictionary is : " + str(test_dict))
print("The original list is : " + str(test_list))

# using zip() and loop to perform 
# combining and assignment respectively.
res = {}
for key, ele in zip(test_list, test_dict.items()):
    res[key] = dict([ele])

# printing result 
print("The mapped dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 4, 'is': 5, 'best': 9}
The original list is : [8, 3, 2]
The mapped dictionary : {8: {'Gfg': 4}, 3: {'is': 5}, 2: {'best': 9}}

```

**方法 2:使用词典理解+ zip()**

这是执行这项任务的另一种方式。在这种情况下，我们执行与上述方法类似的任务，但在一行中使用字典理解

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Nested Dictionary with List
# Using dictionary comprehension + zip()

# initializing dictionary and list
test_dict = {'Gfg' : 4, 'is' : 5, 'best' : 9} 
test_list = [8, 3, 2]

# printing original dictionary and list
print("The original dictionary is : " + str(test_dict))
print("The original list is : " + str(test_list))

# zip() and dictionary comprehension mapped in one liner to solve
res = {idx: {key : test_dict[key]} for idx, key in zip(test_list, test_dict)}

# printing result 
print("The mapped dictionary : " + str(res)) 
```

**Output**

```py
The original dictionary is : {'Gfg': 4, 'is': 5, 'best': 9}
The original list is : [8, 3, 2]
The mapped dictionary : {8: {'Gfg': 4}, 3: {'is': 5}, 2: {'best': 9}}

```