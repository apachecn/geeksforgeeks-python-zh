# Python |区间列表求和

> 原文:[https://www . geesforgeks . org/python-interval-list-summary/](https://www.geeksforgeeks.org/python-interval-list-summation/)

有许多方法可以用元素初始化列表，但有时，需要用分片的方式用数字初始化列表，并找到其总和。这可以是定制的，因此这方面的知识可以派上用场。让我们讨论一下实现这一点的某些方法。

**方法一:使用列表理解+ `enumerate() + sum()`**
列表理解可以做可能的迭代部分，枚举可以帮助逻辑部分和检查列表中所需的有效元素。sum()用于执行求和。

```
# Python3 code to demonstrate 
# Interval List Summation
# using list comprehension + enumerate() + sum()

# initializing lists
test_list = list(range(50))

# printing original list
print ("The original list is : " + str(test_list))

# interval elements
N = 5

# interval difference
K = 15

# using list comprehension + enumerate() + sum()
# Interval List Summation
res = sum([i for j, i in enumerate(test_list) if j % K < N ])

# printing result 
print ("The modified range sum list : " + str(res))
```

**Output :**

> 原来的名单是:[0、1、2、3、4、5、6、7、8、9、10、11、12、13、14、15、16、17、18、19、20、21、22、23、24、25、26、27、28、29、30、31、32、33、34、35、36、37、38、39、40、41、42、43