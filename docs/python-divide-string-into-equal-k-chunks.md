# Python–将字符串分成相等的 K 个块

> 原文:[https://www . geeksforgeeks . org/python-将字符串分成相等的 k 个块/](https://www.geeksforgeeks.org/python-divide-string-into-equal-k-chunks/)

给定一个字符串，将它分成 K 个相等的块。

> **输入** : test_str = 'geeksforgeek '，K = 4
> **输出** : ['gee '，' ksf '，' org '，' eek']
> **解释** : 12/4 = 3，每个字符串提取的长度。
> 
> **输入**:test _ str = ' geesforgek '，K = 1
> **输出**:[' geesforgek ']
> **解释** : 12/1 = 12，整串为单个组块。

**方法#1:使用 len() + loop**

在这种情况下，我们首先执行从 K 和字符串长度中计算每个所需块的长度的任务，然后在期望的索引上分割字符串，以使用切片来提取块。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Divide String into Equal K chunks
# Using len() + loop

# initializing strings
test_str = 'geeksforgeeks 1'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 5

# compute chunk length 
chnk_len = len(test_str) // K

res = []
for idx in range(0, len(test_str), chnk_len):

    # appending sliced string
    res.append(test_str[idx : idx + chnk_len])

# printing result 
print("The K chunked list : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks 1
The K chunked list : ['gee', 'ksf', 'org', 'eek', 's 1']

```

**方法 2:使用列表理解**

方法与上面类似，不同的是最后一个过程被封装成一个线性列表理解。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Divide String into Equal K chunks
# Using list comprehension

# initializing strings
test_str = 'geeksforgeeks 1'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 5

# compute chunk length 
chnk_len = len(test_str) // K

# one-liner to perform the task 
res = [test_str[idx : idx + chnk_len] for idx in range(0, len(test_str), chnk_len)]

# printing result 
print("The K len chunked list : " + str(res)) 
```

**Output**

```
The original string is : geeksforgeeks 1
The K len chunked list : ['gee', 'ksf', 'org', 'eek', 's 1']

```