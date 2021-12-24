# Python–检查第 Kth 个索引元素是否唯一

> 原文:[https://www . geesforgeks . org/python-check-if-kth-index-elements-unique/](https://www.geeksforgeeks.org/python-check-if-kth-index-elements-are-unique/)

给定一个字符串列表，检查是否所有 Kth 索引元素都是唯一的。

> **输入**:test _ list =[“gfg”、“best”、“for”、“geeks”]，K = 1
> **输出** : False
> **说明** : e 在 best 和 geeks 中均作为第一索引出现。
> 
> **输入**:test _ list =[“gfg”、“best”、“极客”]，K = 2
> **输出** : True
> **解释** : g、s、e，都是独一无二的。

**方法#1:使用循环**

这是解决这个问题的粗暴方法。在这种情况下，我们迭代每个字符串，并在任何元素重复时标记为 off，然后返回 false。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Check if Kth index elements are unique
# Using loop

# initializing list
test_list = ["gfg", "best", "for", "geeks"] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

res = []
flag = True
for ele in test_list:

    # checking if element is repeated
    if ele[K] in res:
        flag = False
        break
    else:
        res.append(ele[K])

# printing result 
print("Is Kth index all unique : " + str(flag))
```

**Output**

```
The original list is : ['gfg', 'best', 'for', 'geeks']
Is Kth index all unique : True

```

**方法 2:使用 Counter() + all()**

在这里，我们计算每个字符的频率。在第 Kth 索引处，all()用于检查 Counter 是否小于 2。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Check if Kth index elements are unique
# Using Counter() + all()
from collections import Counter

# initializing list
test_list = ["gfg", "best", "for", "geeks"] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

# getting count of each Kth index item
count = Counter(sub[K] for sub in test_list)

# extracting result 
res = all(val < 2 for val in count.values())

# printing result 
print("Is Kth index all unique : " + str(res))
```

**Output**

```
The original list is : ['gfg', 'best', 'for', 'geeks']
Is Kth index all unique : True

```