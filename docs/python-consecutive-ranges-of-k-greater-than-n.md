# Python–K 大于 N 的连续范围

> 原文:[https://www . geeksforgeeks . org/python-连续-范围-k-大于-n/](https://www.geeksforgeeks.org/python-consecutive-ranges-of-k-greater-than-n/)

给定一个元素列表，任务是编写一个 Python 程序来获取所有大于 n 的 K 的范围

> **输入:**【2，6，6，6，6，5，4，6，6，8，4，6，6，6，2，6】，K = 6，N = 3
> 
> **输出:** [(1，4)，(11，13)]
> 
> **说明:** 6 从索引 1 到 4 连续，因此结果为 1-4。7-8 也有 6 个，但其小于 3 的大小范围，因此不包括在结果中。
> 
> **输入:**【2，1，1，1，1，5，4，1，1】，K = 1，N = 3
> 
> **输出:** [(1，4)]
> 
> **说明:** 1 从索引 1 到 4 是连续的，因此结果为 1-4。7-8 也有 1，但其小于 3 的大小范围，因此不包括在结果中。

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，跟踪 K 的每次出现，并使用嵌套循环来获得范围的大小。如果范围大小大于 N，该范围将记录在结果中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Consecutive Ranges of K greater than N
# Using loop

# initializing list
test_list = [2, 6, 6, 6, 6, 5, 4, 6, 
             6, 8, 4, 6, 6, 6, 2, 6]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 6

# initializing N
N = 3

res = []
strt, end = 0, 0
prev = 1
for idx, ele in enumerate(test_list):

    # if ele K assign end
    if ele == K:
        end = idx

        # if prev ele not K, reassign start
        if prev != K:     # previous item one
            strt = idx
    else:

        # if range is greater than N, append to result
        if prev == K and end - strt + 1 >= N:
            res.append((strt, end))
    prev = ele

# printing result
print("The extracted ranges : " + str(res))
```

**输出:**

> 原来的名单是:[2，6，6，6，6，5，4，6，6，8，4，6，6，6，2，6]
> 
> 提取的范围:[(1，4)，(11，13)]

**方法二:使用** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/)**+**[**zip()**](https://www.geeksforgeeks.org/zip-in-python/)**+**[**列表切片**](https://www.geeksforgeeks.org/python-list-slicing/)**+**[T21】列表理解](https://www.geeksforgeeks.org/python-list-comprehension/)

在这种情况下，K 的所有结束和开始对分别用前一个和下一个元素提取。然后检查配对索引，以确定它们之间是否有所需的范围，从而添加到列表的结果中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Consecutive Ranges of K greater than N
# Using enumerate() + zip() + list slice + list comprehension

# initializing list
test_list = [2, 6, 6, 6, 6, 5, 4, 6, 
             6, 8, 4, 6, 6, 6, 2, 6]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 6

# initializing N
N = 3

# getting break pairs indices
brk_pairs = [idx for idx, (x, y) in enumerate(
    zip(test_list, test_list[1:]), 
  1) if (x == K) != (y == K)]

# The ranges are checked for size required
res = [(idx, ele - 1) for idx, ele in zip([K] + brk_pairs, 
                                          brk_pairs + [len(test_list)])
       if ele - idx >= N and test_list[idx] == K]

# printing result
print("The extracted ranges : " + str(res))
```

**输出:**

> 原来的名单是:[2，6，6，6，6，5，4，6，6，8，4，6，6，6，2，6]
> 
> 提取的范围:[(1，4)，(11，13)]