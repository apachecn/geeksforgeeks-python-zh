# Python–列表中的交叉模式对

> 原文:[https://www . geesforgeks . org/python-交叉模式-列表中的对/](https://www.geeksforgeeks.org/python-cross-pattern-pairs-in-list/)

给定两个列表，以交叉模式对角配对它们[适用于偶数和等长列表]。

> **输入** : test_list1 = [4，5，6，2]，test_list2 = [9，1，4，7]
> **输出** : [(4，1)，(5，9)，(6，7)，(2，4)]
> **解释**:对角交联，4- > 1，5- > 9。
> 
> **输入** : test_list1 = [4，5]，test_list2 = [9，1]
> **输出** : [(4，1)，(5，9)]
> **解释**:对角交联，4- > 1，5- > 9。

**方法#1:使用循环**

在这种情况下，我们遍历列表并测试偶数或奇数索引，在偶数索引的情况下，我们与其他列表的下一个元素配对，或者我们与其他列表的前一个元素配对。这样就形成了交叉模式元组。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Cross Pattern Pairs in List
# Using loop

# function to generate cross pattern pairs
def crossPair(test_list1, test_list2):

    # lengths of both lists should be equal
    if len(test_list1) != len(test_list2):
        return -1

    res = []
    for idx in range(len(test_list1)):

        # checking for conditions
        if idx % 2 == 0:
            res.append((test_list1[idx], test_list2[idx + 1]))
        else:
            res.append((test_list1[idx], test_list2[idx - 1]))
    return res

# initializing lists
input_list1 = [4, 5, 6, 2, 8, 9]
input_list2 = [9, 1, 4, 7, 9, 2]

# printing original lists
print("The original list 1 is : " + str(input_list1))
print("The original list 2 is : " + str(input_list2))

# printing result
print("Paired List elements : ", crossPair(input_list1, input_list2))
```

**输出:**

> 原列表 1 为:[4，5，6，2，8，9]
> 原列表 2 为:[9，1，4，7，9，2]
> 配对列表元素:[(4，1)，(5，9)，(6，7)，(2，4)，(8，2)，(9，9)]

**方法 2:使用列表理解**

使用与上述方法类似的方法，区别是列表理解被用作解决这个问题的单一线性选择。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Cross Pattern Pairs in List
# Using list comprehension

# function to generate cross pattern pairs
def crossPair(test_list1, test_list2):

    # lengths of both lists should be equal
    if len(test_list1) != len(test_list2):
        return -1

    # list comprehension used as one liner alternative
    res = [(test_list1[idx], test_list2[idx + 1]) if idx % 2 ==
           0 else (test_list1[idx], test_list2[idx - 1]) for idx in range(len(test_list1))]
    return res

# initializing lists
input_list1 = [4, 5, 6, 2, 8, 9]
input_list2 = [9, 1, 4, 7, 9, 2]

# printing original lists
print("The original list 1 is : " + str(input_list1))
print("The original list 2 is : " + str(input_list2))

# printing result
print("Paired List elements : ", crossPair(input_list1, input_list2))
```

**输出:**

> 原列表 1 为:[4，5，6，2，8，9]
> 原列表 2 为:[9，1，4，7，9，2]
> 配对列表元素:[(4，1)，(5，9)，(6，7)，(2，4)，(8，2)，(9，9)]