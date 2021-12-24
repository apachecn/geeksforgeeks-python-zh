# Python–连接动态频率

> 原文:[https://www . geesforgeks . org/python-concatenate-dynamic-frequency/](https://www.geeksforgeeks.org/python-concatenate-dynamic-frequency/)

给定元素列表，动态执行与频率的连接，即每个元素与其频率连接，直到其索引。

> **输入** : test_list = ['z '，' z '，' e '，' f '，【f']
> **输出** : ['1z '，' 2z '，' 1e '，' 1f '，' 2f']
> **说明:**随着出现次数增加，多联数增加。
> 
> **输入** : test_list = ['g '，' f '，' g']
> **输出** : ['1g '，' 1f '，' 2g']
> **说明:**随着出现次数增加，串联数增加。

**方法:使用 default dict()+“+”运算符+ str()**

在这种情况下，动态频率计算使用 defaultdict()完成，str()用于将元素转换为字符串，以便使用“+”运算符进行有效连接。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Concatenate Dynamic Frequency
# Using defaultdict() + "+" operator + str()
from collections import defaultdict

# initializing list
test_list = ['z', 'z', 'e', 'f', 'f', 'e', 'f', 'z', 'c']

# printing original list
print("The original list is : " + str(test_list))

memo = defaultdict(int)
res = []
for ele in test_list:
    memo[ele] += 1

    # adding Frequency with element
    res.append(str(memo[ele]) + str(ele))

# printing result 
print("Dynamic Frequency list : " + str(res))
```

**Output**

```
The original list is : ['z', 'z', 'e', 'f', 'f', 'e', 'f', 'z', 'c']
Dynamic Frequency list : ['1z', '2z', '1e', '1f', '2f', '2e', '3f', '3z', '1c']

```