# Python–列表中的累计行频率

> 原文:[https://www . geesforgeks . org/python-累积-行-频率-在列表中/](https://www.geeksforgeeks.org/python-cumulative-row-frequencies-in-list/)

给定 Matrix，任务是编写一个 Python 程序来获取该行的总出现次数。

> **输入** : test_list = [[10，2，3，2，3]，[5，5，4，7，7，4]，[1，2]，[1，1，2，2，2，2]]，ele_list = [1，2，7]
> **输出** : [2，2，2，5]
> **解释** : 2 在第 1 行出现 2 次，以此类推。
> 
> **输入** : test_list = [[10，2，3，2，3]，[5，5，4，7，7，4]]，ele_list = [1，2，7]
> **输出** : [2，2]
> **解释** : 2 在第 1 行出现 2 次，以此类推。

**方法一:使用** [**计数器()**](https://www.geeksforgeeks.org/counters-in-python-set-1/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，我们执行获取所有行的所有频率的任务，然后从行中检查所需元素的列表出现，sum()用于获取行中提取频率的总和。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Cumulative Row Frequencies
# Using Counter() + list comprehension
from collections import Counter 

# initializing list
test_list = [[10, 2, 3, 2, 3], 
             [5, 5, 4, 7, 7, 4], 
             [1, 2], [1, 1, 2, 2, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing ele_list 
ele_list = [1, 2, 7]

# getting each rows counter 
freqs = [Counter(ele) for ele in test_list]

# getting summation of present values 
res = [sum([freq[wrd] for wrd in ele_list if wrd in freq]) for freq in freqs]

# printing result 
print("Cumulative Frequencies : " + str(res))
```

**输出:**

> 原始列表为:[[10，2，3，2，3]，[5，5，4，7，7，4]，[1，2]，[1，1，2，2，2]]
> 累计频率:[2，2，2，5]

**方法二:使用** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/) **+列表理解**

在本文中，我们使用 sum()执行获取求和的任务，列表理解用于检查检查列表中的元素并遍历行。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Cumulative Row Frequencies
# Using sum() + list comprehension

# initializing list
test_list = [[10, 2, 3, 2, 3], 
             [5, 5, 4, 7, 7, 4],
             [1, 2], [1, 1, 2, 2, 2]]

# printing original list
print("The original list is : " + str(test_list))

# initializing ele_list 
ele_list = [1, 2, 7]

# getting summation 
res = [sum(ele in ele_list for ele in sub) for sub in test_list]

# printing result 
print("Cumulative Frequencies : " + str(res))
```

**输出:**

> 原始列表为:[[10，2，3，2，3]，[5，5，4，7，7，4]，[1，2]，[1，1，2，2，2]]
> 累计频率:[2，2，2，5]