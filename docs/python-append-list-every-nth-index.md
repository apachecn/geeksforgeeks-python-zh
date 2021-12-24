# Python–每第 n 个索引追加一个列表

> 原文:[https://www . geesforgeks . org/python-append-list-隔 n 次-index/](https://www.geeksforgeeks.org/python-append-list-every-nth-index/)

给定 2 个列表，每第 n 个索引将列表追加到原始列表中。

> **输入** : test_list = [3，7，8，2，1，5，8]，app_list = ['G '，' F '，' G']，N = 3
> **输出** : ['G '，' F '，' G '，3，7，8，' G '，' F '，' G '，2，1，5，' G '，' F '，' G '，8]
> **说明**:列表每第 3 个元素后增加一个。
> **输入** : test_list = [3，7，8，2，1，5，8，9]，app_list = ['G '，' F '，' G']，N = 4
> **输出** : ['G '，' F '，' G '，3，7，8，2，' G '，' F '，' G '，1，5，8，9 'G '，' F '，' G']
> **说明**:列表每第 4 个元素后增加一个。

**方法#1:使用循环**

这是解决这个问题的蛮方法，在这种情况下，每第 n 个索引，内部循环用于追加所有其他列表元素。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Append List every Nth index
# Using loop

# initializing list
test_list = [3, 7, 8, 2, 1, 5, 8, 9, 3]

# printing original list
print("The original list is : " + str(test_list))

# initializing Append list 
app_list = ['G', 'F', 'G']

# initializing N 
N = 3

res = []
for idx, ele in enumerate(test_list):

    # if index multiple of N
    if idx % N == 0:
        for ele_in in app_list:
            res.append(ele_in)
    res.append(ele)

# printing result 
print("The appended list : " + str(res))
```

**输出:**

> 原名单为:【3、7、8、2、1、5、8、9、3】
> 后附名单:【‘G’，‘F’，‘G’，3、7、8，‘G’，‘F’，‘G’，2、1、5，‘G’，‘F’，‘G’，8、9、3】

**方法 2:使用 extend()**

解决这个问题的另一种方法。在这种情况下，我们使用扩展来获取每个第 n 个索引中的所有元素，而不是内部列表。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Append List every Nth index
# Using extend()

# initializing list
test_list = [3, 7, 8, 2, 1, 5, 8, 9, 3]

# printing original list
print("The original list is : " + str(test_list))

# initializing Append list 
app_list = ['G', 'F', 'G']

# initializing N 
N = 3

res = []
for idx, ele in enumerate(test_list):

    # if index multiple of N
    if idx % N == 0:

        # extend to append all elements
        res.extend(app_list)

    res.append(ele)

# printing result 
print("The appended list : " + str(res))
```

**输出:**

> 原名单为:【3、7、8、2、1、5、8、9、3】
> 后附名单:【‘G’，‘F’，‘G’，3、7、8，‘G’，‘F’，‘G’，2、1、5，‘G’，‘F’，‘G’，8、9、3】