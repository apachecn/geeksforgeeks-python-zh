# Python–从字符串列表中提取连续相似元素范围

> 原文:[https://www . geeksforgeeks . org/python-提取-连续相似元素的范围-范围-从字符串列表/](https://www.geeksforgeeks.org/python-extract-range-of-consecutive-similar-elements-ranges-from-string-list/)

给定一个列表，提取连续相似元素的范围。

> **输入** : test_list = [2，3，3，3，8，8]
> **输出** : [(2，0，0)，(3，1，3)，(8，4，5)]
> **解释** : 2 出现在第 0 到第 0 个索引，3 出现在第 1 到第 3 个索引。
> 
> **输入** : test_list = [3，3，3]
> **输出** : [(3，0，3)]
> **解释** : 3 从第 0 到第 3 个指标。

**进场:使用循环**

这是解决这个问题的粗暴方法。在这种情况下，我们对每个元素进行循环，得到一个相似的元素范围。这些被跟踪并相应地以元素形式附加在列表中。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Consecutive Similar elements ranges
# Using loop

# initializing list
test_list = [2, 3, 3, 3, 8, 8, 6, 7, 7]

# printing original list
print("The original list is : " + str(test_list))

res = []
idx = 0
while idx < (len(test_list)):
    strt_pos = idx
    val = test_list[idx]

    # getting last pos.
    while (idx < len(test_list) and test_list[idx] == val): 
        idx += 1
    end_pos = idx - 1

    # appending in format [ele, strt_pos, end_pos]
    res.append((val, strt_pos, end_pos))

# printing result 
print("Elements with range : " + str(res))
```

**输出:**

> 原列表为:【2，3，3，3，8，8，6，7，7】
> 范围内的元素:[(2，0，0)，(3，1，3)，(8，4，5)，(6，6，6)，(7，7，8)]