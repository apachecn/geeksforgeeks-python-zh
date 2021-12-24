# Python–分组连接直到 K

> 原文:[https://www . geesforgeks . org/python-group-concatenate-till-k/](https://www.geeksforgeeks.org/python-group-concatenate-till-k/)

给定字符串列表，分组执行连接，直到 k

> **输入**:test _ list =[“Gfg”、“is”、“Best”、“”、“I”、“Love”、“”、“Gfg”]、K =“
> **输出**:[‘Gfg 是 Best’，‘I Love’，‘Gfg’]
> **解释**:串接单词用“”作为新的字符串分隔符。
> 
> **输入**:test _ list =[“Gfg”、“is”、“Best”、“”、“I”、“Love”]、K =“
> **输出**:[“Gfg 是 Best”、“I Love”]
> **解释**:以“”为新字符串分隔符的串联词。

**方法:使用循环+连接()+列表理解**

这是执行这项任务的一种方式。在本文中，我们将部分字符串构造成列表，然后使用 join()和列表理解来执行单个列表的连接。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Group concatenate Till K 
# Using loop + join() + list comprehension

# initializing lists
test_list = ["Gfg", "is", "Best", None, "I", "Love", None, "Gfg"]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = None

# all() to encapsulate whole logic into one expression
res = [[]]
for sub in test_list:

    # checking for K value, and performing append to 
    # latest list 
    if sub != K:
        res[-1].append(sub)
    else:

        # constructing new list if new group
        res.append([])

# Joining all groups 
fin_res = [' '.join(ele) for ele in res]

# printing result 
print("Concatenated Groups : " + str(fin_res))
```

**Output**

```py
The original list : ['Gfg', 'is', 'Best', None, 'I', 'Love', None, 'Gfg']
Concatenated Groups : ['Gfg is Best', 'I Love', 'Gfg']

```