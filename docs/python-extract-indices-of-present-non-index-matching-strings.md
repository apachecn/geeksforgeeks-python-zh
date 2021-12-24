# Python–提取当前非索引匹配字符串的索引

> 原文:[https://www . geesforgeks . org/python-extract-indexes-of-present-non-index-matching-strings/](https://www.geeksforgeeks.org/python-extract-indices-of-present-non-index-matching-strings/)

给定两个字符串，从字符串 1 中提取出现在其他字符串中但不在同一索引中的所有字符的索引。

> **输入** : test_str1 = 'pplg '，test_str2 = '菠萝'
> **输出**:【0，1，2】
> **解释** : ppl 在第二个字符串中找到，也不在第一个字符串的同一索引上。
> 
> **输入** : test_str1 = '松树'，test_str2 = '菠萝'
> **输出** : []
> **解释**:在同一索引的其他字符串中找到。

**方法#1:使用 enumerate() +循环**

在这种情况下，我们使用嵌套循环来检查每个字符在第二个字符串中的出现，然后如果它在其他位置，如果找到了，则添加索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract indices of Present, Non Index matching Strings
# using loop + enumerate()

# initializing strings
test_str1 = 'apple'
test_str2 = 'pineapple'

# printing original Strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# the replaced result 
res = []
for idx, val in enumerate(test_str1):

    # if present in string 2
    if val in test_str2:

        # if not present at same index
        if test_str2[idx] != val:      
            res.append(idx)

# printing result 
print("The extracted indices : " + str(res)) 
```

**Output**

```py
The original string 1 is : apple
The original string 2 is : pineapple
The extracted indices : [0, 1, 2, 3, 4]

```

**方法二:使用 enumerate() + zip() +列表理解**

在本文中，我们使用 enumerate()执行获取索引的任务，两个字符串的配对使用 zip()完成，条件检查使用列表理解进行。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Extract indices of Present, Non Index matching Strings
# using enumerate() + zip() + list comprehension

# initializing strings
test_str1 = 'apple'
test_str2 = 'pineapple'

# printing original Strings
print("The original string 1 is : " + str(test_str1))
print("The original string 2 is : " + str(test_str2))

# one-liner to solve this problem.
res = [idx for idx, (x, y) in enumerate(zip(test_str1, test_str2)) if x != y and x in test_str2]

# printing result 
print("The extracted indices : " + str(res)) 
```

**Output**

```py
The original string 1 is : apple
The original string 2 is : pineapple
The extracted indices : [0, 1, 2, 3, 4]

```