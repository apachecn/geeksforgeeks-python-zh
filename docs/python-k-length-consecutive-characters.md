# Python–K 长度连续字符

> 原文:[https://www . geesforgeks . org/python-k-length-continuous-characters/](https://www.geeksforgeeks.org/python-k-length-consecutive-characters/)

给定一个字符串，提取所有 K 长度的连续字符。

> **输入**:test _ str = ' geekforgeekss 为 bbbest forrr geeks '，K = 3
> **输出** : ['eee '，' sss '，' bbb '，' rrr']
> **解释**:提取 K 长度连续字符串。
> 
> **输入**:test _ str = ' geekforgeekss 为 bbbest forrrr geeks '，K = 4
> **输出** : ['rrrr']
> **解释**:提取 K 长度连续字符串。

**方法#1:使用循环**

在这种情况下，我们维护计数器来检查元素的连续性，如果它们在单独的元素之前正好等于 K，那么返回数字，它自己追加 K 次。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# K length consecutive characters
# Using loop

# initializing string
test_str = 'geekforgeeekssss is bbbbest forrrr geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 4

res = []
curr, cnt = None, 0
for chr in test_str:

    # increment for similar character
    if chr == curr:
        cnt += 1
    else:
        curr, cnt = chr, 1

    # if count exactly K, element is added
    if cnt == K:
        res.append(K * chr)

# printing result 
print("The K length similar characters : " + str(res)) 
```

**Output**

```
The original string is : geekforgeeekssss is bbbbest forrrrrrr geeks
The K length similar characters : ['ssss', 'bbbb', 'rrrr']

```

**方法 2:使用 split() + enumerate()**

在这种情况下，我们从每个索引创建子串，如果这些子串的每个元素都相等，那么它就返回到结果。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# K length consecutive characters
# Using split() + enumerate()

# initializing string
test_str = 'geekforgeeekssss is bbbbest forrrr geeks'

# printing original string
print("The original string is : " + str(test_str))

# initializing K 
K = 4

res = []
for idx, ele in enumerate(test_str):

    # creating equi string 
    substr = ele * K

    # checking if equal to actual string 
    if test_str[idx : idx + K] == substr:
        res.append(substr)

# printing result 
print("The K length similar characters : " + str(list(set(res)))) 
```

**Output**

```
The original string is : geekforgeeekssss is bbbbest forrrrrrr geeks
The K length similar characters : ['bbbb', 'ssss', 'rrrr']

```