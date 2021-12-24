# Python |从列表中查找重叠元组

> 原文:[https://www . geesforgeks . org/python-find-重叠-元组-from-list/](https://www.geeksforgeeks.org/python-find-overlapping-tuples-from-list/)

有时，在处理元组数据时，我们可能会遇到一个问题，即我们可能需要获取与某个元组重叠的元组。使用几何时，这种问题可能会出现在数学领域。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环**
在该方法中，我们使用条件语句提取具有重叠的对，并将合适的匹配附加到列表保存记录中。

```py
# Python3 code to demonstrate working of
# Find overlapping tuples from list
# using loop 

# initialize list
test_list = [(4, 6), (3, 7), (7, 10), (5, 6)]

# initialize test tuple 
test_tup = (1, 5)

# printing original list
print("The original list : " + str(test_list))

# Find overlapping tuples from list
# using loop 
res = []
for tup in test_list:
    if(tup[1]>= test_tup[0] and tup[0]<= test_tup[1]):
        res.append(tup)

# printing result
print("The tuple elements that overlap the argument tuple is : "
                                                     + str(res))
```

**Output :**

> 原列表:[(4，6)，(3，7)，(7，10)，(5，6)]
> 与自变量元组重叠的元组元素为:[(4，6)，(3，7)，(5，6)]