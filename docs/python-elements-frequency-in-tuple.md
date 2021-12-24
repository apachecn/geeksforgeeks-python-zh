# Python–元组中的元素频率

> 原文:[https://www . geesforgeks . org/python-elements-in-frequency-in-tuple/](https://www.geeksforgeeks.org/python-elements-frequency-in-tuple/)

给定一个元组，找出每个元素的频率。

> **输入** : test_tup = (4，5，4，5，6，6，5)
> **输出** : {4: 2，5: 3，6: 2}
> **解释**:4 的频率为 2 等等..
> **输入** : test_tup = (4，5，4，5，6，6，6)
> **输出** : {4: 2，5: 2，6: 3}
> **解释**:4 的频率为 2 等等..

**方法#1 使用 defaultdict()**

在这种情况下，我们使用 defaultdict 执行获取所有元素并分配频率的任务，default dict 用键映射每个元素，然后频率可以增加。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Elements frequency in Tuple
# Using defaultdict()
from collections import defaultdict

# initializing tuple
test_tup = (4, 5, 4, 5, 6, 6, 5, 5, 4)

# printing original tuple
print("The original tuple is : " + str(test_tup))

res = defaultdict(int)
for ele in test_tup:

    # incrementing frequency
    res[ele] += 1

# printing result
print("Tuple elements frequency is : " + str(dict(res)))
```

**Output**

```
The original tuple is : (4, 5, 4, 5, 6, 6, 5, 5, 4)
Tuple elements frequency is : {4: 3, 5: 4, 6: 2}
```

**方法 2:使用计数器()**

这是解决这个问题的直截了当的方法。在这种情况下，我们只使用这个函数，它返回容器中元素的频率，在这种情况下是元组。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Elements frequency in Tuple
# Using Counter()
from collections import Counter

# initializing tuple
test_tup = (4, 5, 4, 5, 6, 6, 5, 5, 4)

# printing original tuple
print("The original tuple is : " + str(test_tup))

# converting result back from defaultdict to dict
res = dict(Counter(test_tup))

# printing result
print("Tuple elements frequency is : " + str(res))
```

**Output**

```
The original tuple is : (4, 5, 4, 5, 6, 6, 5, 5, 4)
Tuple elements frequency is : {4: 3, 5: 4, 6: 2}
```