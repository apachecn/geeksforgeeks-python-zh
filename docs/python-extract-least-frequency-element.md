# Python |提取最少频率元素

> 原文:[https://www . geesforgeks . org/python-extract-最小频率-element/](https://www.geeksforgeeks.org/python-extract-least-frequency-element/)

有时，在处理数据时，我们可能会遇到这样的问题:我们需要提取列表中出现次数最少的元素。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用`defaultdict()` +循环**
上述功能的组合可用于执行该任务。在本文中，我们使用 defaultdict()提取每个元素的频率，并在遍历 defaultdict 之后提取最小频率元素。

```
# Python3 code to demonstrate working of
# Extract least frequency element
# using defaultdict() + loop
from collections import defaultdict

# initialize list 
test_list = [1, 3, 4, 5, 1, 3, 5]

# printing original list 
print("The original list : " + str(test_list))

# Extract least frequency element
# using defaultdict() + loop
res = defaultdict(int)
for ele in test_list:
   res[ele] += 1 
min_occ = 9999
for ele in res:
    if min_occ > res[ele]:
        min_occ = res[ele]
        tar_ele = ele

# printing result
print("The minimum occurring element is : " + str(tar_ele))
```

**Output :**

```
The original list : [1, 3, 4, 5, 1, 3, 5]
The minimum occurring element is : 4

```