# Python |查找大于 K 的最小元素

> 原文:[https://www . geesforgeks . org/python-find-minimal-element-大于-k/](https://www.geeksforgeeks.org/python-find-smallest-element-greater-than-k/)

给定一个列表，编写一个 Python 程序来查找大于特定元素 k 的最小数字

让我们看看解决这个问题的所有方法，从简单到单行，以便在需要时可以在编程中使用。

**方法#1:天真的方法**
使用循环，如果我们发现元素小于命名变量的前一个值并且大于 k，我们继续重新初始化命名变量

```
# Python3 code to demonstrate 
# smallest number greater than K
# using naive method 

# Initializing list 
test_list = [1, 4, 7, 5, 10]

# Initializing k
k = 6

# Printing original list 
print ("The original list is : " + str(test_list))

# Using naive method 
# to find smallest number
# greater than K
min_val = 10000000
for i in test_list :
    if min_val > i and i > k :
        min_val = i

# Printing result 
print ("The minimum value greater than 6 is : " + str(min_val))
```

**输出:**

```
The original list is : [1, 4, 7, 5, 10]
The minimum value greater than 6 is : 7

```

**方法 2:使用`min()` +生成器表达式**
`min()`返回序列中的最小数，并将其与生成器表达式相耦合，可以更简洁地执行此任务，因此在需要节省时间时更有用。

```
# Python3 code to demonstrate 
# smallest number greater than K
# using min() + generator expression

# Initializing list 
test_list = [1, 4, 7, 5, 10]

# Initializing k
k = 6

# Printing original list 
print ("The original list is : " + str(test_list))

# Using min() + generator expression
# to find smallest number
# greater than K
min_val = min(i for i in test_list if i > k)

# Printing result 
print ("The minimum value greater than 6 is : " + str(min_val))
```

**输出:**

```
The original list is : [1, 4, 7, 5, 10]
The minimum value greater than 6 is : 7

```

**方法#3 : `min() + filter()`**
类似于上面的方法，只是为了过滤列表中大于 k 的数字，在这个方法中使用了`filter()` 代替生成器表达式。工作方式与上面类似。

```
# Python3 code to demonstrate 
# smallest number greater than K
# using min() + filter()

# Initializing list 
test_list = [1, 4, 7, 5, 10]

# Initializing k
k = 6

# Printing original list 
print ("The original list is : " + str(test_list))

# Using min() + filter()
# to find smallest number
# greater than K
min_val = min(filter(lambda i: i > k, test_list))

# Printing result 
print ("The minimum value greater than 6 is : " + str(min_val))
```

**输出:**

```
The original list is : [1, 4, 7, 5, 10]
The minimum value greater than 6 is : 7

```

**方法#4:利用`sort() + bisect_right()`**
`bisect_right()`再加上`sort()`为我们执行二分搜索法的任务，也因此是实现这个问题解决的一个不错的选择。`bisect_right()` 因为它返回严格意义上更大的数字，而不是列表中存在的数字本身。

```
# Python3 code to demonstrate 
# smallest number greater than K
# using sort() + bisect_right()
from bisect import bisect_right

# Initializing list 
test_list = [1, 4, 7, 5, 10]

# Initializing k
k = 6

# Printing original list 
print ("The original list is : " + str(test_list))

# Using sort() + bisect_right()
# to find smallest number
# greater than K
test_list.sort()
min_val = test_list[bisect_right(test_list, k)]

# Printing result 
print ("The minimum value greater than 6 is : " + str(min_val))
```

**输出:**

```
The original list is : [1, 4, 7, 5, 10]
The minimum value greater than 6 is : 7

```