# Python–切片字符串中 K 的频率

> 原文:[https://www . geeksforgeeks . org/python-切片字符串中 k 的频率/](https://www.geeksforgeeks.org/python-frequency-of-k-in-sliced-string/)

给定一个字符串，在索引范围内找到某个字符的频率。

> **输入** : test_str = 'geeksforgeeks 最适合极客'，i = 3，j = 9，K = 'e'
> **输出** : 0
> **解释**:第 4 个【s】和第 9 个元素之间没有出现' e '。[e]。
> 
> **输入** : test_str = 'geeksforgeeks 最适合极客'，i = 0，j = 9，K = 'e'
> **输出** : 2
> **解释** : e 呈现为第 2、3 元素。

**方法#1:使用切片和计数()**

在这种情况下，我们使用切片操作对所需的字符串进行切片，然后使用 coun()获取切片字符串中的 K 计数。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Frequency of K in sliced String
# Using slicing + count()

# initializing strings
test_str = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing i, j
i, j = 3, 20

# initializing K 
K = 'e'

# slicing String 
slc = test_str[i : j]

# using count() to get count of K 
res = slc.count(K)

# printing result 
print("The required Frequency : " + str(res)) 
```

**Output**

```py
The original string is : geeksforgeeks is best for geeks
The required Frequency : 3

```

**方法 2:使用 Counter() +切片**

在本例中，我们使用 Counter()执行获取计数的任务，切片用于执行范围切片。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Frequency of K in sliced String
# Using Counter() + slicing 
from collections import Counter

# initializing strings
test_str = 'geeksforgeeks is best for geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing i, j
i, j = 3, 20

# initializing K 
K = 'e'

# slicing String 
slc = test_str[i : j]

# Counter() is used to get count 
res = Counter(slc)[K]

# printing result 
print("The required Frequency : " + str(res)) 
```

**Output**

```py
The original string is : geeksforgeeks is best for geeks
The required Frequency : 3

```