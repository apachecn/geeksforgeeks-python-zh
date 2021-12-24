# Python |检查列表中 k 是否至少出现 n 次

> 原文:[https://www . geesforgeks . org/python-check-if-k-occurs-至少 n 次在列表中/](https://www.geeksforgeeks.org/python-check-if-k-occurs-atleast-n-times-in-a-list/)

在日常编码中，开发人员或普通程序员会遇到许多常见的问题。一个这样的问题是发现一个元素在列表中出现的次数是否超过一定次数。让我们讨论处理这个问题的某些方法。

**方法#1 :** 使用`sum()` +列表理解
列表理解可以用求和函数来实现这个特定的任务。求和函数做求和部分，返回真的逻辑情况在列表理解部分处理。

```py
# Python3 code to demonstrate 
# check for minimum N occureneces of K 
# using sum() + list comprehension

# initializing list
test_list = [1, 3, 5, 5, 4, 5]

# printing original list
print ("The original list is : " + str(test_list))

# initializing k 
k = 5

# initializing N
N = 3

# using sum() + list comprehension
# checking occurrences of K atleast N times 
res = 0
res = sum([1 for i in test_list if i == k]) >= N
if res == 1 :
    res = True
else : 
    res = False

# printing result 
print ("Does %d occur atleast %d times ? :" %(k, N) + str(res))
```

**Output:**

```py
The original list is : [1, 3, 5, 5, 4, 5]
Does 5 occur atleast 3 times ? : True

```

**方法 2 :** 使用`next() + islice()`
这两个功能可以一起使用，以比上面更有效的方式执行这个特定的任务。`islice` 函数将处理求和部分，下一个函数有助于迭代逻辑。

```py
# Python3 code to demonstrate 
# check for minimum N occureneces of K 
# using next() + islice()
from itertools import islice

# initializing list
test_list = [1, 3, 5, 5, 4, 5]

# printing original list
print ("The original list is : " + str(test_list))

# initializing k 
k = 5

# initializing N
N = 3

# using next() + islice()
# checking occurrences of K atleast N times 
func = (True for i in test_list if i == k)
res = next(islice(func, N-1, None), False)

# printing result 
print ("Does %d occur atleast %d times ? :" %(k, N) + str(res))
```

**Output:**

```py
The original list is : [1, 3, 5, 5, 4, 5]
Does 5 occur atleast 3 times ? : True

```