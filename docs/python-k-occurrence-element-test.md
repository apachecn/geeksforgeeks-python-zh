# Python | K 出现元素测试

> 原文:[https://www . geesforgeks . org/python-k-occurrence-element-test/](https://www.geeksforgeeks.org/python-k-occurrence-element-test/)

在日常编码中，开发人员或普通程序员会遇到许多常见的问题。一个这样的问题是发现一个元素是否在列表中出现了一定次数。让我们讨论处理这个问题的某些方法。

**方法#1:使用`sum()` +列表理解**
列表理解可以用求和函数来实现这个特定的任务。求和函数做求和部分，返回真的逻辑情况在列表理解部分处理。

```
# Python3 code to demonstrate 
# K occurrence element Test
# using sum() + list comprehension

# initializing list
test_list = [1, 3, 5, 5, 4, 5]

# printing original list
print ("The original list is : " + str(test_list))

# initializing k 
k = 3

# initializing N
N = 5

# using sum() + list comprehension
# K occurrence element Test 
res = 0
res = sum([1 for i in test_list if i == N]) == k
if res == 1 :
    res = True
else : 
    res = False

# printing result 
print ("Does N occur K times ? : " + str(res))
```

**Output :**

```
The original list is : [1, 3, 5, 5, 4, 5]
Does N occur K times ? : True

```