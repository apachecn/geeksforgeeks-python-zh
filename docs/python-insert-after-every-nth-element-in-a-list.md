# Python–在列表中每第 n 个元素后插入

> 原文:[https://www . geesforgeks . org/python-每第 n 个列表元素后插入/](https://www.geeksforgeeks.org/python-insert-after-every-nth-element-in-a-list/)

有时我们需要在 python 中执行一次插入，这可以在 insert 函数的帮助下轻松完成。但有时，我们需要在每 n 个数字后重复插入，因为可能会有许多人手不够用的地方。让我们讨论一下实现这一点的某些方法。

**方法#1:使用`join() + enumerate()`**
我们可以使用 join 函数将第 n 个子串中的每一个与数字 K 连接起来，并枚举可以执行列表选择性迭代的任务。

```py
# Python3 code to demonstrate 
# inserting K after every Nth number
# using join() + enumerate()

# initializing list
test_list = ['g', 'e', 'e', 'k', 's', 'f', 'o', 'r',
                            'g', 'e', 'e', 'k', 's']

# printing original list
print ("The original list is : " + str(test_list))

# initializing k 
k = 'x'

# initializing N
N = 3

# using join() + enumerate()
# inserting K after every Nth number 
res = list(''.join(i + k * (N % 3 == 2) 
           for N, i in enumerate(test_list)))

# printing result 
print ("The lists after insertion : " +  str(res))
```

**Output:**

> 原列表为:['g '，' e '，' e '，' k '，' s '，' f '，' o '，' r '，' g '，' e '，' e '，' k '，' s']
> 插入后的列表:['g '，' e '，' e '，' e '，' x '，' k '，' s '，' f '，' x '，' o '，' r '，' g '，' x '，' e '，' k '，' s']