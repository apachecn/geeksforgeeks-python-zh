# Python | N 个列表的所有可能排列方式

> 原文:[https://www . geesforgeks . org/python-n 列表的所有可能排列/](https://www.geeksforgeeks.org/python-all-possible-permutations-of-n-lists/)

计算置换一直是许多实际应用中的必要任务，也是数学中广泛使用的一个概念，用来解决许多实际问题。让我们讨论一些方法，通过这些方法我们可以完成获取 N 个列表的所有排列的任务。

**方法#1:使用列表理解**
列表理解可以将幼稚的方法任务转换成单行，因此更加紧凑。此方法检查每个元素是否有可用元素，并相应地进行配对。

```py
# Python3 code to demonstrate 
# to compute all possible permutations
# using list comprehension 

# initializing lists
list1 = [1, 3, 4]
list2 = [6, 7, 9]
list3 = [8, 10, 5]

# printing lists 
print ("The original lists are : " + str(list1) +
                               " " + str(list2) + 
                               " " + str(list3))

# using list comprehension 
# to compute all possible permutations
res = [[i, j, k] for i in list1 
                 for j in list2
                 for k in list3]

# printing result
print ("All possible permutations are : " +  str(res))
```

**输出:**

> 原始列表为:[1，3，4] [6，7，9] [8，10，5]
> 所有可能的排列为:[[1，6，8]，[1，6，10]，[1，6，5]，[1，7，8]，[1，7，10]，[1，7，5]，[1，9，8]，[1，9，10]，[1，9，5]，[3，6，8]，[3，6，10]，[3 6, 5], [4, 7, 8], [4, 7, 10], [4, 7, 5], [4, 9, 8], [4, 9, 10], [4, 9, 5]]

**方法 2:使用`itertools.product()`**
使用产品功能，可以更简洁明了地轻松完成这项任务。这是执行计算笛卡儿积任务最推荐的方法。

```py
# Python3 code to demonstrate 
# to compute all possible permutations
# using itertools.product() 
import itertools

# initializing list of list 
all_list = [[1, 3, 4], [6, 7, 9], [8, 10, 5] ]

# printing lists 
print ("The original lists are : " + str(all_list))

# using itertools.product()  
# to compute all possible permutations
res = list(itertools.product(*all_list))

# printing result
print ("All possible permutations are : " +  str(res))
```

**输出:**

> 原始列表为:[[1，3，4]，[6，7，9]，[8，10，5]]
> 所有可能的排列为:[(1，6，8)，(1，6，10)，(1，6，5)，(1，7，8)，(1，7，10)，(1，7，5)，(1，9，8)，(1，9，10)，(1，9，5)，(3，6，8)，(3，6，10)，(3，6，5)，(3，7，8)，(3，7，8) 6, 5), (4, 7, 8), (4, 7, 10), (4, 7, 5), (4, 9, 8), (4, 9, 10), (4, 9, 5)]