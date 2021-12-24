# Python–通过符号对连续元素进行分组

> 原文:[https://www . geesforgeks . org/python-group-continuous-elements-by-sign/](https://www.geeksforgeeks.org/python-group-consecutive-elements-by-sign/)

给定一组基于符号的连续元素列表。

> **输入** : test_list = [5，-3，2，4，6，-2，-1，-7，-9，2，3]
> **输出** : [[5]，[-3]，[2，4，6]，[-2，-1，-7，-9]，[2，3]]
> **解释**:符号变更时插入新列表的元素。
> 
> **输入** : test_list = [-2，3，4，5，6，-3]
> **输出**:[-2]，[3，4，5，6]，[-3]]
> **解释**:符号变化时插入新列表的元素。

**方法#1:使用循环**

在这种情况下，每当符号(正或负)发生变化时，就会启动一个新的列表，否则元素会被附加到一个与初始化时相似的列表中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Group Consecutive elements by Sign
# Using loop

# initializing list
test_list = [5, -3, 2, 4, 6, -2, -1, -7, 
             -9, 2, 3, 10, -3, -5, 3]

# printing original list
print("The original list is : " + str(test_list))

res = [[]]
for (idx, ele) in enumerate(test_list):

    # checking for similar signs by XOR
    if ele ^ test_list[idx - 1] < 0:
        res.append([ele])
    else:
        res[-1].append(ele)

# printing result 
print("Elements after sign grouping : " + str(res))
```

**输出:**

> 原列表为:【5，-3，2，4，6，-2，-1，-7，-9，2，3，10，-3，-5，3】
> 符号分组后的元素:[[5]，[-3]，[2，4，6]，[-2，-1，-7，-9]，[2，3，10]，[-3，-5]，[3]]

**方法二:使用 groupby() +列表理解**

在本文中，我们使用 groupby()执行分组任务，使用列表理解来执行遍历列表的任务。使用 lambda 函数注入符号的条件。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Group Consecutive elements by Sign
# Using groupby() + list comprehension
import itertools

# initializing list
test_list = [-2, 3, 4, 5, 6, -3]

# printing original list
print("The original list is : " + str(test_list))

# grouped using groupby()
res = [list(ele) for idx, ele in itertools.groupby(test_list, lambda a: a > 0)]

# printing result
print("Elements after sign grouping : " + str(res))
```

**输出:**

> 原列表为:[-2，3，4，5，6，-3]
> 符号分组后的元素:[-2]，[3，4，5，6]，[-3]]