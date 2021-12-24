# Python–字符的连续重复

> 原文:[https://www . geesforgeks . org/python-连续重复字符/](https://www.geeksforgeeks.org/python-consecutive-repetition-of-characters/)

有时，在处理字符列表时，我们会遇到一个问题，即我们需要连续重复字符。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法一:使用列表理解**
这是可以执行这个任务的方式之一。在这种情况下，我们使用暴力的方式来执行，但是通过将每个字符乘以大小来形成一行。

```py
# Python3 code to demonstrate working of 
# Consecutive Repetition of  Characters
# Using list comprehension

# initializing list
test_list = ['g', 'f', 'g', 'i', 's', 'b', 'e', 's', 't']

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

# Consecutive Repetition of  Characters
# Using list comprehension
res = [sub for ele in test_list for sub in [ele] * K]

# printing result 
print("The list after Consecutive Repetition is : " + str(res)) 
```

**Output :**

> 原列表为:['g '，' f '，' g '，' I '，' s '，' b '，' e '，' s '，' t']
> 连续重复后的列表为:['g '，' g '，' g '，' f '，' f '，' f '，' g '，' g '，' g '，' g '，' I '，' I '，' I '，' s '，' s '，' t '，' t']