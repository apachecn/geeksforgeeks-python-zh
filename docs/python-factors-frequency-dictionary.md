# Python–因子频率字典

> 原文:[https://www . geesforgeks . org/python-factors-frequency-dictionary/](https://www.geeksforgeeks.org/python-factors-frequency-dictionary/)

给定一个包含元素的列表，构建一个包含频率因子的字典。

> **输入** : test_list = [2，4，6，8]
> **输出** : {1: 4，2: 4，3: 1，4: 2，5: 0，6: 1，7: 0，8: 1}
> **解释**:所有因子都被映射，例如 2 可以被所有 4 个值整除，因此被映射为 4。
> 
> **输入**:test _ list =【1，2】
> **输出** : {1: 2，2 : 1}
> **解释**:同上，1 为全因子。

**方法#1:使用循环**

这是执行这项任务的粗暴方式。在这种情况下，对元素进行迭代，并检查所需的数量是否是一个因素，如果是，则在与其关键字对应的字典中增加其频率。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Factors Frequency Dictionary
# Using loop

# initializing list
test_list = [2, 4, 6, 8, 3, 9, 12, 15, 16, 18]

# printing original list
print("The original list : " + str(test_list))

res = dict()

# iterating till max element 
for idx in range(1, max(test_list)):
    res[idx] = 0
    for key in test_list:

        # checking for factor 
        if key % idx == 0:
            res[idx] += 1

# printing result 
print("The constructed dictionary : " + str(res))
```

**Output**

```py
The original list : [2, 4, 6, 8, 3, 9, 12, 15, 16, 18]
The constructed dictionary : {1: 10, 2: 7, 3: 6, 4: 4, 5: 1, 6: 3, 7: 0, 8: 2, 9: 2, 10: 0, 11: 0, 12: 1, 13: 0, 14: 0, 15: 1, 16: 1, 17: 0}

```

**方法 2:使用 sum() +循环**

这几乎与上述问题相似。差 sum()用于求和，而不是用于解决问题的手动循环。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Factors Frequency Dictionary
# Using sum() + loop

# initializing list
test_list = [2, 4, 6, 8, 3, 9, 12, 15, 16, 18]

# printing original list
print("The original list : " + str(test_list))

res = dict()
for idx in range(1, max(test_list)):

    # using sum() instead of loop for sum computation
    res[idx] = sum(key % idx == 0 for key in test_list)

# printing result 
print("The constructed dictionary : " + str(res))
```

**Output**

```py
The original list : [2, 4, 6, 8, 3, 9, 12, 15, 16, 18]
The constructed dictionary : {1: 10, 2: 7, 3: 6, 4: 4, 5: 1, 6: 3, 7: 0, 8: 2, 9: 2, 10: 0, 11: 0, 12: 1, 13: 0, 14: 0, 15: 1, 16: 1, 17: 0}

```