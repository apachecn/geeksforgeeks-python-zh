# Python–将每个列表元素转换为键值对

> 原文:[https://www . geesforgeks . org/python-convert-ever-list-element-to-key-value-pair/](https://www.geeksforgeeks.org/python-convert-each-list-element-to-key-value-pair/)

给定元素列表，将每个元素转换为键值对字典，将数字等分。

> **输入** : test_list = [2323，82，129388，234，95]
> **输出** : {23: 23，8: 2，129: 388，2: 34，9: 5}
> **解释**:数字平均分配给键和值。
> 
> **输入**:test _ list =【2323，82，129388】
> **输出** : {23: 23，8: 2，129: 388}
> **解释**:数字平均分配给键和值。

**方法:使用列表切片+循环**

在这种情况下，我们通过将键和值的数字除以一半，从每个元素中获得分片值，从而形成键-值对。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Convert each list element to key-value pair
# Using loop + list slicing

# initializing list
test_list = [2323, 82, 129388, 234, 95]

# printing original list
print("The original list is : " + str(test_list))

res = dict()
for ele in test_list:

    # constructing key and values
    mid_idx = len(str(ele)) // 2
    key = int(str(ele)[:mid_idx])
    val = int(str(ele)[mid_idx:])

    # item assignment
    res[key] = val

# printing result
print("Constructed Dictionary : " + str(res))
```

**Output**

```
The original list is : [2323, 82, 129388, 234, 95]
Constructed Dictionary : {23: 23, 8: 2, 129: 388, 2: 34, 9: 5}

```