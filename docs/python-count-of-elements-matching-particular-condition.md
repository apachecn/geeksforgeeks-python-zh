# Python |匹配特定条件的元素计数

> 原文:[https://www . geesforgeks . org/python-元素计数-匹配-特定条件/](https://www.geeksforgeeks.org/python-count-of-elements-matching-particular-condition/)

按条件检查数字/元素是一个人面临的常见问题，几乎在每个程序中都要做。有时，我们还需要获得与特定条件匹配的总数，以便区分哪些不匹配，以便进一步利用。让我们讨论一下完成这项任务的某些方法。

**方法#1:使用`sum()` +生成器表达式**
每当生成器表达式返回 true 时，该方法就使用总和加 1 的技巧。当列表耗尽时，返回与条件匹配的数字总数。

```
# Python 3 code to demonstrate 
# to get count of elements matching condition 
# using sum() + generator expression

# initializing list
test_list = [3, 5, 1, 6, 7, 9]

# printing original list
print ("The original list is : " + str(test_list))

# using sum() + generator expression
# to get count of elements matching condition 
# checks for odd
res = sum(1 for i in test_list if i % 2 != 0)

# printing result
print ("The number of odd elements: " + str(res))
```

**输出:**

```
The original list is : [3, 5, 1, 6, 7, 9]
The number of odd elements: 5

```

**方法 2:使用`sum()` + `map()`** `map()`完成的任务几乎类似于生成器表达式，不同的只是它采用的内部数据结构不同因此效率更高。

```
# Python 3 code to demonstrate 
# to get count of elements matching condition 
# using sum()+ map()

# initializing list
test_list = [3, 5, 1, 6, 7, 9]

# printing original list
print ("The original list is : " + str(test_list))

# using sum()+ map()
# to get count of elements matching condition 
# checks for odd
res = sum(map(lambda i: i % 2 != 0, test_list))

# printing result
print ("The number of odd elements: " + str(res))
```

**输出:**

```
The original list is : [3, 5, 1, 6, 7, 9]
The number of odd elements: 5

```

**方法 3:使用`reduce() + lamda`**
reduce 函数在上面使用的方法中作为 sum 函数完成累加任务。lambda 用于执行需要检查结果的条件。

```
# Python 3 code to demonstrate 
# to get count of elements matching condition 
# using reduce() + lambda

# initializing list
test_list = [3, 5, 1, 6, 7, 9]

# printing original list
print ("The original list is : " + str(test_list))

# using reduce() + lambda
# to get count of elements matching condition 
# checks for odd
res = reduce(lambda count, i: count + (i % 2 != 0), test_list, 0)

# printing result
print ("The number of odd elements: " + str(res))
```

**输出:**

```
The original list is : [3, 5, 1, 6, 7, 9]
The number of odd elements: 5

```