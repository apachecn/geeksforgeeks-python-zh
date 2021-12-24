# Python–从元组列表中分配对元素

> 原文:[https://www . geesforgeks . org/python-assign-pair-elements-from-tuple-list/](https://www.geeksforgeeks.org/python-assign-pair-elements-from-tuple-lists/)

给定一个元组列表，为每个元素分配来自其他相似元素对的元素对。

> **输入** : test_list = [(5，3)，(7，5)，(8，4)]
> **输出** : {5: [3]，7: [5]，8: [4]，4: []}
> **解释**:第 1 个元素与所有元组中相应的第 2 个元素配对。
> 
> **输入** : test_list = [(5，3)]
> **输出** : {5: [3]}
> **解释**:只有一个元组，5 和 3 配对。

**方法:使用 setdefault() +循环**

在这种情况下，我们使用暴力的方式来解决这个问题，迭代每个元组，并将每个键和值的默认值设置为空列表，如果元素已经存在，则将元素追加到相应的列表中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Assign pair elements from Tuple Lists
# Using setdefault + loop

# initializing list
test_list = [(5, 3), (7, 5), (2, 7), (3, 8), (8, 4)]

# printing string
print("The original list : " + str(test_list))

# initializing dictionary
res = dict()
for key, val in test_list:

    # adding to both, corresponding keys and values
    res.setdefault(val, [])
    res.setdefault(key, []).append(val)

# printing results 
print("The resultant pairings : " + str(res))
```

**Output**

```
The original list : [(5, 3), (7, 5), (2, 7), (3, 8), (8, 4)]
The resultant pairings : {3: [8], 5: [3], 7: [5], 2: [7], 8: [4], 4: []}

```