# Python–将相似项目分组到字典值列表中

> 原文:[https://www . geesforgeks . org/python-group-相似项-到-字典-值-列表/](https://www.geeksforgeeks.org/python-group-similar-items-to-dictionary-values-list/)

给定一个元素列表，对相似的元素进行分组，作为字典中不同的键值列表。

> **输入** : test_list = [4，6，6，4，2，2，4，8，5，8]
> **输出** : {4: [4，4，4]，6: [6，6]，2: [2，2]，8: [8，8]，5: [5]}
> **解释**:出现时相似的项目分组在一起。
> 
> **输入** : test_list = [7，7，7，7]
> **输出** : {7 : [7，7，7，7]，7]}
> **解释**:出现时分组在一起的相似项目。

**方法#1:使用 defaultdict() +循环**

这是执行这项任务的方法之一。在  这个中，我们构造用缺省列表构造一个 defaultdict()，并不断将相似的值追加到相似的列表中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Group Similar items to Dictionary Values List
# Using defaultdict + loop
from collections import defaultdict

# initializing list
test_list = [4, 6, 6, 4, 2, 2, 4, 4, 8, 5, 8]

# printing original list
print("The original list : " + str(test_list))

# using defaultdict for default list 
res = defaultdict(list)
for ele in test_list:

    # appending Similar values
    res[ele].append(ele)

# printing result 
print("Similar grouped dictionary : " + str(dict(res)))
```

**Output**

```
The original list : [4, 6, 6, 4, 2, 2, 4, 4, 8, 5, 8]
Similar grouped dictionary : {4: [4, 4, 4, 4], 6: [6, 6], 2: [2, 2], 8: [8, 8], 5: [5]}

```

**方法 2:使用词典理解+ Counter()**

这是执行这项任务的另一种方式。在本文中，我们使用 Counter()提取频率，然后使用乘法重复出现。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Group Similar items to Dictionary Values List
# Using dictionary comprehension + Counter()
from collections import Counter

# initializing list
test_list = [4, 6, 6, 4, 2, 2, 4, 4, 8, 5, 8]

# printing original list
print("The original list : " + str(test_list))

# using * operator to perform multiplication
res = {key : [key] * val for key, val in Counter(test_list).items()}

# printing result 
print("Similar grouped dictionary : " + str(res))
```

**Output**

```
The original list : [4, 6, 6, 4, 2, 2, 4, 4, 8, 5, 8]
Similar grouped dictionary : {4: [4, 4, 4, 4], 6: [6, 6], 2: [2, 2], 8: [8, 8], 5: [5]}

```