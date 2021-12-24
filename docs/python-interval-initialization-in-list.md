# Python |列表中的区间初始化

> 原文:[https://www . geesforgeks . org/python-interval-initiation-in-list/](https://www.geeksforgeeks.org/python-interval-initialization-in-list/)

有许多方法可以用元素初始化列表，但是有时，需要用切片的方式用数字初始化列表。这可以是定制的，因此这方面的知识可以派上用场。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`list comprehension + enumerate()`**
列表理解可以做可能的迭代部分，枚举可以帮助逻辑部分和检查列表中所需的有效元素。

```
# Python3 code to demonstrate 
# interval initializing in list 
# using list comprehension + enumerate()

# initializing lists
test_list = list(range(50))

# printing original list
print ("The original list is : " + str(test_list))

# interval elements
N = 5

# interval difference
K = 15

# using list comprehension + enumerate()
# interval initializing in list 
res =  [i for j, i in enumerate(test_list) if j % K < N ]

# printing result 
print ("The modified initialized list : " +  str(res))
```

**输出:**

> 原来的名单是:[0、1、2、3、4、5、6、7、8、9、10、11、12、13、14、15、16、17、18、19、20、21、22、23、24、25、26、27、28、29、30、31、32、33、34、35、36、37、38、39、40、41、42、43

**方法 2:使用`itertools.compress() + itertools.cycle()`**
以上两个功能可以结合起来，方便解决所讨论的问题。循环功能可用于重复任务，压缩功能在将片段组合在一起时会很有用。

```
# Python3 code to demonstrate 
# interval initializing in list 
# using itertools.compress() + itertools.cycle()
from itertools import compress, cycle 

# initializing lists
test_list = list(range(50))

# printing original list
print ("The original list is : " + str(test_list))

# interval elements
N = 5

# interval difference
K = 15

# using itertools.compress() + itertools.cycle()
# interval initializing in list 
func = cycle([True] * N + [False] * (K - N))
res = list(compress(test_list, func))

# printing result 
print ("The modified initialized list : " +  str(res))
```

**输出:**

> 原来的名单是:[0、1、2、3、4、5、6、7、8、9、10、11、12、13、14、15、16、17、18、19、20、21、22、23、24、25、26、27、28、29、30、31、32、33、34、35、36、37、38、39、40、41、42、43