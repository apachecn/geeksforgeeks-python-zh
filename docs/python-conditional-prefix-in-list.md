# Python–列表中的条件前缀

> 原文:[https://www . geesforgeks . org/python-条件前缀在列表中/](https://www.geeksforgeeks.org/python-conditional-prefix-in-list/)

给定一个元素列表，根据条件附加不同的前缀。

> **输入** : test_list = [45，53，76，86，3，49]，pref _ 1 =“LOSE-”，pref _ 2 =“WIN-”
> **输出** : ['LOSE-45 '，' WIN-53 '，' WIN-76 '，' WIN-86 '，' los-3 '，' LOSE-49']
> **解释**:所有 50+前缀为“WIN-”，其他为“LOSE-”。
> 
> **输入** : test_list = [78，53，76，86，83，69]，pref _ 1 =“LOSE-”，pref _ 2 =“WIN-”
> **输出** : ['WIN-78 '，' WIN-53 '，' WIN-76 '，' WIN-86 '，' WIN-83 '，' WIN-69']
> **说明:**均为 50+因此前缀为“WIN-”。

**方法#1:使用循环**

执行这项任务的粗暴方式。在本文中，我们使用条件运算符和循环来执行前缀匹配任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Conditional Prefix in List
# Using loop

# initializing list
test_list = [45, 53, 76, 86, 3, 49]

# printing original list
print("The original list : " + str(test_list))

# initializing pref 1
pref_1 = "LOW-"

# initializing pref 2
pref_2 = "HIGH-"

res = []
for ele in test_list:

    # appending prefix on greater than 50 check
    if ele >= 50:
        res.append(pref_2 + str(ele))
    else :
        res.append(pref_1 + str(ele))

# printing result 
print("The prefixed elements : " + str(res))
```

**Output**

```py
The original list : [45, 53, 76, 86, 3, 49]
The prefixed elements : ['LOW-45', 'HIGH-53', 'HIGH-76', 'HIGH-86', 'LOW-3', 'LOW-49']

```

**方法 2:使用列表理解**

这是执行这项任务的方法之一。在这种情况下，我们使用列表理解来执行与上面类似的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Conditional Prefix in List
# Using list comprehension

# initializing list
test_list = [45, 53, 76, 86, 3, 49]

# printing original list
print("The original list : " + str(test_list))

# initializing pref 1
pref_1 = "LOW-"

# initializing pref 2
pref_2 = "HIGH-"

# solution encapsulated as one-liner and conditional checks
res = [pref_2 + str(ele) if ele >= 50 else pref_1 + str(ele) for ele in test_list]

# printing result 
print("The prefixed elements : " + str(res))
```

**Output**

```py
The original list : [45, 53, 76, 86, 3, 49]
The prefixed elements : ['LOW-45', 'HIGH-53', 'HIGH-76', 'HIGH-86', 'LOW-3', 'LOW-49']

```