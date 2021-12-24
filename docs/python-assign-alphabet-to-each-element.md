# Python–为每个元素分配字母表

> 原文:[https://www . geesforgeks . org/python-给每个元素分配字母/](https://www.geeksforgeeks.org/python-assign-alphabet-to-each-element/)

给定一个元素列表，给同一个元素分配相似的字母表。

> **输入** : test_list = [4，5，2，4，2，6]
> **输出** : ['a '，' b '，' c '，' a '，' c '，' d']
> **解释**:分配给发生元素的字母。
> 
> **输入** : test_list = [4，5，2，4，2，6]
> **输出** : ['a '，' b '，' c '，' a '，' c']
> **解释**:出现时分配给元素的字母。

**方法一:使用 ascii _ 小写()+循环+列表理解**

在本文中，我们使用小写()提取所有小写字母，并创建将相同元素映射到相似字符的字典，然后使用列表理解将该字典展平为适当的索引。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Assign Alphabet to each element
# Using ascii_lowercase() + loop + list comprehension
import string

# initializing list
test_list = [4, 5, 2, 4, 2, 6, 5, 2, 5]

# printing list
print("The original list : " + str(test_list))

temp = {}
cntr = 0
for ele in test_list:
    if ele in temp:
        continue

    # assigning same Alphabet to same element
    temp[ele] = string.ascii_lowercase[cntr]
    cntr += 1

# flattening
res = [temp.get(ele) for ele in test_list]

# printing results
print("The mapped List : " + str(res))
```

**Output**

```
The original list : [4, 5, 2, 4, 2, 6, 5, 2, 5]
The mapped List : ['a', 'b', 'c', 'a', 'c', 'd', 'b', 'c', 'b']
```

**方法 2:使用 default dict()+ascii _ 小写()+ iter()**

在本文中，我们使用 defaultdict()为相似的元素赋值，ascii _ lotter()用于获取所有小写字母。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Assign Alphabet to each element
# Using defaultdict() + ascii_lowercase() + iter()
from collections import defaultdict
import string

# initializing list
test_list = [4, 5, 2, 4, 2, 6, 5, 2, 5]

# printing list
print("The original list : " + str(test_list))

# assigning lowercases as iterator
temp = iter(string.ascii_lowercase)

# lambda functions fits to similar elements
res = defaultdict(lambda: next(temp))

# flatten in list
res = [res[key] for key in test_list]

# printing results
print("The mapped List : " + str(list(res)))
```

**Output**

```
The original list : [4, 5, 2, 4, 2, 6, 5, 2, 5]
The mapped List : ['a', 'b', 'c', 'a', 'c', 'd', 'b', 'c', 'b']
```