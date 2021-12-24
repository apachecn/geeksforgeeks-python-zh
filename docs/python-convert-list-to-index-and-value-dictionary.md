# Python–将列表转换为索引和值字典

> 原文:[https://www . geesforgeks . org/python-convert-list-to-index-value-dictionary/](https://www.geeksforgeeks.org/python-convert-list-to-index-and-value-dictionary/)

给定一个列表，将其转换为字典，并为索引和值提供单独的键。

> **输入** : test_list = [3，5，7，8，2，4，9]，idx，val = "1 "，" 2"
> **输出** : {'1': [0，1，2，3，4，5，6]，' 2': [3，5，7，8，2，4，9]}
> **解释**:diff 中相似索引处映射的索引和值。钥匙。，为“1”和“2”。
> 
> **输入** : test_list = [3，5，7]，idx，val =“1”，“2”
> **输出** : {'1': [0，1，2]，' 2': [3，5，7]}
> **解释**:diff 中相似索引处映射的索引和值。钥匙。，为“1”和“2”。

**方法:使用循环+枚举()**

在本文中，我们使用 enumerate()迭代列表元素，以获得索引和值，并相应地在单独的字典中追加相应的值和索引。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert List to Index and Value dictionary
# Using loop + enumerate()

# initializing list
test_list = [3, 5, 7, 8, 2, 4, 9]

# printing original list
print("The original list is : " + str(test_list))

# initializing keys for index and vals 
idx, val = "indx", "vals"

# initializing empty mesh
res = {idx : [], val : []}
for id, vl in enumerate(test_list):
    res[idx].append(id)
    res[val].append(vl)

# printing results
print("Constructed dictionary : " + str(res))
```

**Output**

```
The original list is : [3, 5, 7, 8, 2, 4, 9]
Constructed dictionary : {'indx': [0, 1, 2, 3, 4, 5, 6], 'vals': [3, 5, 7, 8, 2, 4, 9]}

```