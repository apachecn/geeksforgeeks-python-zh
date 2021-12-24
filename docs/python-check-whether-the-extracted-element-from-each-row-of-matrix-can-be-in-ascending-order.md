# Python–检查矩阵每行提取的元素是否可以升序

> 原文:[https://www . geesforgeks . org/python-check-矩阵每行提取的元素是否可以按升序排列/](https://www.geeksforgeeks.org/python-check-whether-the-extracted-element-from-each-row-of-matrix-can-be-in-ascending-order/)

给定一个矩阵，这里的任务是首先从每一行中选择一个元素，这样，当按照精确的顺序排列时，它们可能会形成一个排序列表或一个升序列表。如果可能，返回真，否则返回假。

> **输入** : test_list = [[3，4，6，2]，[3，4，9，1]，[8，5，4，7]，[9，1，2，3]]
> 
> **输出:**真
> 
> **说明:**【2，3，4，9】是可能增加的列表。
> 
> **输入:** test_list = [[3，4，6，2]，[3，4，9，1]，[8，5，4，7]，[1，1，2，3]]
> 
> **输出:**假
> 
> **说明:**增加列表不可能。

**方法:** *使用* [*循环*](https://www.geeksforgeeks.org/loops-in-python/) *和* [*min()*](https://www.geeksforgeeks.org/python-min-function/)

在这种情况下，我们不断更新每一行中的最小可能元素，如果最小元素大于前一个元素，则找不到最小值，结果被标记为 false，表示不可能出现升序列表。

**程序:**

## 蟒蛇 3

```
# initializing list
test_list = [[3, 4, 6, 2], [3, 4, 9, 1], [8, 5, 4, 7], [9, 1, 2, 3]]

# printing original list
print("The original list is : " + str(test_list))

# initializing with min of 1st row
cur = min(test_list[0])

res = True
for sub in test_list[1:]:
    res = False

    # checking row for greater than previous minimum
    for idx in sub:
        if idx >= cur:
            res = True

            # storing new minimum
            cur = idx
            break

    if not res:
        break

# printing result
print("Is ascending list possible ? : " + str(res))
```

**输出:**

> 原来的名单是:[[3，4，6，2]，[3，4，9，1]，[8，5，4，7]，[9，1，2，3]]
> 
> 升序列表可能吗？:真