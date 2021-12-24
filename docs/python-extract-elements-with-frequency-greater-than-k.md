# Python–提取频率大于 K 的元素

> 原文:[https://www . geesforgeks . org/python-extract-elements-with-frequency-大于-k/](https://www.geeksforgeeks.org/python-extract-elements-with-frequency-greater-than-k/)

给定一个列表，提取频率大于 k 的所有元素

> **输入**:test _ list =【4，6，4，3，3，4，3，8】，K = 3
> **输出**:【4，3】
> **解释**:两个元素出现 4 次。
> 
> **输入**:test _ list =【4、6、4、3、3、4、4、6、6】，K = 2
> **输出**:【4、3、6】
> **解释**:分别出现 4、3、3 次。

**方法#1:使用 count() +循环**

在这种情况下，我们使用 count()来获取频率，并使用循环来迭代 List 的每个元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract elements with Frequency greater than K
# Using count() + loop

# initializing list
test_list = [4, 6, 4, 3, 3, 4, 3, 7, 8, 8]

# printing string
print("The original list : " + str(test_list))

# initializing K 
K = 2

res = [] 
for i in test_list: 

    # using count() to get count of elements
    freq = test_list.count(i) 

    # checking if not already entered in results
    if freq > K and i not in res: 
        res.append(i)

# printing results 
print("The required elements : " + str(res))
```

**Output**

```py
The original list : [4, 6, 4, 3, 3, 4, 3, 7, 8, 8]
The required elements : [4, 3]

```

**方法 2:使用列表理解+计数器()**

在本文中，我们使用 Counter()执行计数任务，迭代部分在列表理解中完成。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract elements with Frequency greater than K
# Using list comprehension + Counter()
from collections import Counter

# initializing list
test_list = [4, 6, 4, 3, 3, 4, 3, 7, 8, 8]

# printing string
print("The original list : " + str(test_list))

# initializing K 
K = 2

# using list comprehension to bind result
res = [ele for ele, cnt in Counter(test_list).items() if cnt > K]

# printing results 
print("The required elements : " + str(res))
```

**Output**

```py
The original list : [4, 6, 4, 3, 3, 4, 3, 7, 8, 8]
The required elements : [4, 3]

```