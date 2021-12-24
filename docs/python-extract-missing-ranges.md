# Python–提取缺失范围

> 原文:[https://www . geesforgeks . org/python-extract-missing-ranges/](https://www.geeksforgeeks.org/python-extract-missing-ranges/)

给定元组列表、开始范围和结束范围值，提取列表中缺少的范围。

> **输入** : test_list = [(7，2)，(15，19)，(38，50)]，strt_val = 5，stop_val = 60
> **输出** : [(5，7)，(2，60)，(2，15)，(19，60)，(19，38)，(50，60)]
> **解释**:从 5 开始到 50-60 结束的缺失元素范围根据需要输出。
> 
> **输入** : test_list = [(7，2)，(15，19)，(38，50)]，strt_val = 1，stop_val = 52
> **输出** : [(1，7)，(2，60)，(2，15)，(19，60)，(19，38)，(50，52)]
> **:同上，只是范围有所改动。**

****方法:使用循环**
这是可以执行该任务的蛮力方法。在这种情况下，我们跟踪开始和停止值，并不断添加缺失的范围。最后，重要的是检查是否有任何范围小于更高的范围。**

```
# Python3 code to demonstrate working of 
# Extract Missing Ranges
# Using loop

# initializing lists
test_list = [(6, 9), (15, 34), (48, 70)]

# printing original list
print("The original list is : " + str(test_list))

# initializing start val 
strt_val = 2

# initializing stop val 
stop_val = 100

# Using loop
res = []
for sub in test_list:

    # checking for start range
    if sub[0] > strt_val:
        res.append((strt_val, sub[0]))
        strt_val = sub[1]

    # checking for end range
    if strt_val < stop_val:
        res.append((strt_val, stop_val))

# printing result 
print("Missing range tuples : " + str(res)) 
```

****Output :**

```
The original list is : [(6, 9), (15, 34), (48, 70)]
Missing range tuples : [(2, 6), (9, 100), (9, 15), (34, 100), (34, 48), (70, 100)]

```**