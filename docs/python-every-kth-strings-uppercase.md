# Python–每第 Kth 个字符串大写

> 原文:[https://www . geesforgeks . org/python-ever-kth-strings-大写/](https://www.geeksforgeeks.org/python-every-kth-strings-uppercase/)

给定一个字符串列表，将每个 Kth 字符串改为大写。

> **输入**:test _ list =[“gfg”、“is”、“best”、“for”、“geeks”]，K = 3
> **输出**:[‘GFG’、‘is’、‘best’、‘FOR’、‘geeks’]
> **解释**:所有 Kth 字符串均大写。
> 
> **输入**:test _ list =[“gfg”、“is”、“best”、“for”、“GEEKS”]，K = 4
> **输出**:[‘GFG’、‘is’、‘best’、‘for’、‘GEEKS’]
> **解释**:所有 Kth 字符串均大写。

**方法#1:使用 loop + upper()**

在这种情况下，我们使用循环对所有字符串进行迭代，使用大写来执行大写，使用模运算符来检测 Kth 索引。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Every Kth Strings Uppercase
# Using loop + upper()

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks", "and", "CS"] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

res = []
for idx in range(len(test_list)):

    # checking for Kth index
    if idx % K == 0:
        res.append(test_list[idx].upper())
    else :
        res.append(test_list[idx])

# printing result 
print("The resultant String list : " + str(res))
```

**Output**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'geeks', 'and', 'CS']
The resultant String list : ['GFG', 'is', 'best', 'FOR', 'geeks', 'and', 'CS']

```

**方法 2:使用列表理解**

这是执行该任务的又一种方式。在本文中，我们使用列表理解作为速记，执行类似于上述方法的任务。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Every Kth Strings Uppercase
# Using list comprehension

# initializing list
test_list = ["gfg", "is", "best", "for", "geeks", "and", "CS"] 

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3

# shorthand to perform this task
res = [test_list[idx].upper() if idx % K == 0 else test_list[idx]
       for idx in range(len(test_list))]

# printing result 
print("The resultant String list : " + str(res))
```

**Output**

```py
The original list is : ['gfg', 'is', 'best', 'for', 'geeks', 'and', 'CS']
The resultant String list : ['GFG', 'is', 'best', 'FOR', 'geeks', 'and', 'CS']

```