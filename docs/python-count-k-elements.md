# Python–计算% K 个元素

> 原文:[https://www.geeksforgeeks.org/python-count-k-elements/](https://www.geeksforgeeks.org/python-count-k-elements/)

按条件检查数字/元素是一个人面临的常见问题，几乎在每个程序中都要做。有时，我们还需要获得与特定条件匹配的总数，以便区分哪些不匹配，以便进一步利用。让我们讨论检查可被 K 整除的数的计数的任务可以实现的某些方法。

**方法#1:使用`sum()` +生成器表达式**
每当生成器表达式返回 true 时，该方法就使用总和加 1 的技巧。当列表耗尽时，返回与% K 匹配的数字总数。

```
# Python 3 code to demonstrate 
# Count % K elements
# using sum() + generator expression

# initializing list
test_list = [3, 5, 1, 6, 7, 9]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K 
K = 3

# using sum() + generator expression
# to get count of elements matching condition 
# Count % K elements
res = sum(1 for i in test_list if i % K != 0)

# printing result
print ("The number of % K elements: " + str(res))
```

**Output :**

```
The original list is : [3, 5, 1, 6, 7, 9]
The number of % K elements: 3

```