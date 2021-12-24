# Python–其他列表中元素的频率

> 原文:[https://www . geesforgeks . org/python-其他元素的频率列表/](https://www.geeksforgeeks.org/python-frequency-of-elements-from-other-list/)

给定两个列表，计算列表 2 中的元素在列表 1 中出现的频率。

> **输入** : test_list1 = [4，6，8，9]，test_list2 = [4，6，6，5，8，10，4，9，8，10，1]
> **输出** : {4: 2，6: 2，8: 2，9: 1}
> **解释**:第二个列表中 4 出现 2 次，6 出现 2 次，以此类推。
> 
> **输入** : test_list1 = [4，6，8，9]，test_list2 = [4，6，5，8，10，4，9，8，10，1]
> **输出** : {4: 2，6: 1，8: 2，9: 1}
> **解释**:第二个列表中 4 出现 2 次，6 出现 1 次等等。

**方法一:使用词典理解+计数()**

这是执行这项任务的方法之一。在这种情况下，count()用于提取列表 2 中元素的计数，字典理解用于编译结果并迭代列表 1 的值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Frequency of elements from other list
# Using dictionary comprehension + count()

# initializing lists
test_list1 = [4, 6, 8, 9, 10]
test_list2 = [4, 6, 6, 5, 8, 10, 4, 9, 8, 10, 1]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# count() used to perform count.
# returns 0 is no occurrence.
# ignores different new elements in list 2
res = {key : test_list2.count(key) for key in test_list1}

# printing result 
print("Lists elements Frequency : " + str(res))
```

**Output**

```
The original list 1 : [4, 6, 8, 9, 10]
The original list 2 : [4, 6, 6, 5, 8, 10, 4, 9, 8, 10, 1]
Lists elements Frequency : {4: 2, 6: 2, 8: 2, 9: 1, 10: 2}

```

**方法 2:使用 Counter() + setdefault() +循环**

这是执行该任务的另一种方式。在本文中，我们使用 Counter()计算频率，并使用 loop 赋值。对于不存在的值，setdefault()用于将计数器初始化为 0。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Frequency of elements from other list
# Using Counter() + setdefault() + loop
from collections import Counter

# initializing lists
test_list1 = [4, 6, 8, 9, 10]
test_list2 = [4, 6, 6, 5, 8, 10, 4, 9, 8, 10, 1]

# printing original lists
print("The original list 1 : " + str(test_list1))
print("The original list 2 : " + str(test_list2))

# Counter() used to perform count on list 2
res = dict(Counter(test_list2))

# filtering only list 1 keys
res = {key : val for key, val in res.items() if key in test_list1} 

for key in test_list1:

    # initializing elements not present in list 2 of list 1 to 0
    res.setdefault(key, 0) 

# printing result 
print("Lists elements Frequency : " + str(res))
```

**Output**

```
The original list 1 : [4, 6, 8, 9, 10]
The original list 2 : [4, 6, 6, 5, 8, 10, 4, 9, 8, 10, 1]
Lists elements Frequency : {4: 2, 6: 2, 8: 2, 10: 2, 9: 1}

```