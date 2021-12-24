# Python–将列表中的每个递增和递减运行分组

> 原文:[https://www . geesforgeks . org/python-group-各增各减-在列表中运行/](https://www.geeksforgeeks.org/python-group-each-increasing-and-decreasing-run-in-list/)

给定一个列表，任务是编写一个 Python 程序，对每个递增和递减的运行进行分组。这就是所谓的单调分组。如果一个列表是单调递增或单调递减的，那么它就是单调的。如果所有的 I<= j, A[i] >= A【j】，列表 A 是单调递减的。

**示例:**

> **输入:** test_list = [5，6，2，9，7，1，10，4，2，1，11，12，2]
> 
> **输出:** [[5，6]，[2]，[9]，[7，1]，[10]，[4，2，1]，[11，12]，[2]]
> 
> **说明:** 6 > 5 然后 2 小于 6，因此变小，开始新组。2 和 9 是峰值或过渡元素，属于单个组。
> 
> **输入:** test_list = [5，6，2，9，7，1，10，4，2，1]
> 
> **输出:** [[5，6]，[2]，[9]，[7，1]，[10]，[4，2，1]]
> 
> **说明:** 6 > 5 然后 2 小于 6，因此变小，开始新组。2 和 9 是峰值或过渡元素，属于单个组。

**示例:使用** [**循环**](https://www.geeksforgeeks.org/understanding-for-loop-in-python/)**+**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)

在这种情况下，从第 0 个和第 1 个索引开始的每两个列表都被压缩，然后将两个列表中的每个元素进行比较，以检查运行并相应地更改标志。初始标志值是根据前两个元素中的哪一个更大来评估的，之后该标志被切换为具有适当的运行分组。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Monotonous grouping in List
# Using loop + zip()

# initializing list
test_list = [5, 6, 2, 9, 7, 1, 10, 4, 2, 1, 11, 12, 2]

# printing original list
print("The original list is : " + str(test_list))

res = []
temp = []
is_up = True 
if test_list[0] > test_list[1]:
    is_up = False
for curr, nex in zip(test_list, test_list[1:]):
    temp.append(curr)

    # checking for increasing or decreasing to change list
    if (nex > curr and not is_up) or (nex < curr and is_up):
        res.append(temp)
        temp = []

        # toggling 
        is_up = not is_up

temp.append(nex)
res.append(temp)

# printing result
print("Monotonous grouping : " + str(res))
```

**输出:**

> 原来的名单是:[5，6，2，9，7，1，10，4，2，1，11，12，2]
> 
> 单调分组:[[5，6]，[2]，[9]，[7，1]，[10]，[4，2，1]，[11，12]，[2]