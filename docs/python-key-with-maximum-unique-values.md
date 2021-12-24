# Python–具有最大唯一值的键

> 原文:[https://www . geesforgeks . org/python-带最大唯一值的密钥/](https://www.geeksforgeeks.org/python-key-with-maximum-unique-values/)

给定带有值列表的字典，提取其值具有最多唯一值的键。

> **输入**:test _ dict = {“Gfg”:[5，7，9，4，0]，“is”:[6，7，4，3，3]，“Best”:[9，9，6，5，5]}
> **输出**:“Gfg”
> **解释**:“Gfg”具有最大唯一元素即 5。
> 
> **输入**:test _ dict = {“Gfg”:[5，7，7，7，7]，“is”:[6，7，7，7]，“Best”:[9，9，6，5，5]}
> **输出**:“Best”
> **解释** : 3 个(最大)唯一元素，9，6，5 个“Best”。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，我们迭代所有列表值，并检查每个键的值计数，提取具有最大唯一值的键。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Key with maximum unique values
# Using loop

# initializing dictionary
test_dict = {"Gfg" : [5, 7, 5, 4, 5],
             "is" : [6, 7, 4, 3, 3], 
             "Best" : [9, 9, 6, 5, 5]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

max_val = 0
max_key = None 
for sub in test_dict:

    # test for length using len()
    # converted to set for duplicates removal
    if len(set(test_dict[sub])) > max_val:
        max_val = len(set(test_dict[sub]))
        max_key = sub

# printing result 
print("Key with maximum unique values : " + str(max_key)) 
```

**Output**

> 原始字典为:{'Gfg': [5，7，5，4，5]，' is': [6，7，4，3，3]，' Best': [9，9，6，5，5]}
> 最大唯一值为的键:is

**方法 2:使用排序的()+lambda()+set()+values()+len()**

上述功能的组合可以用来解决这个问题。在这种情况下，我们根据设置的长度对字典关键字进行反向排序，并返回第一个结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Key with maximum unique values
# Using sorted() + lambda() + set() + values() + len()

# initializing dictionary
test_dict = {"Gfg" : [5, 7, 5, 4, 5],
             "is" : [6, 7, 4, 3, 3], 
             "Best" : [9, 9, 6, 5, 5]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# one-liner to solve a problem
# sorted used to reverse sort dictionary
max_key = sorted(test_dict, key = lambda ele: len(
          set(test_dict[ele])), reverse = True)[0]

# printing result 
print("Key with maximum unique values : " + str(max_key)) 
```

**Output**

> 原始字典为:{'Gfg': [5，7，5，4，5]，' is': [6，7，4，3，3]，' Best': [9，9，6，5，5]}
> 最大唯一值为的键:is