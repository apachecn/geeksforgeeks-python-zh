# Python–列映射元组到字典项目

> 原文:[https://www . geesforgeks . org/python-column-mapped-元组-to-dictionary-items/](https://www.geeksforgeeks.org/python-column-mapped-tuples-to-dictionary-items/)

给定长度为 2 的元组矩阵，将每列的元素值映射到下一列，并构造字典键。

> **输入**:test _ list =[(1，4)，(6，3)，(4，7)]，[(7，3)，(10，14)，(11，22)]
> **输出** : {1: 7，4: 3，6: 10，3: 14，4: 11，7: 22}
> **解释** : 1 - > 7，4 - > 3..，如在同一列和索引中。
> 
> **输入**:test _ list =[(1，4)，(6，3)]，[(7，3)，(10，14)]
> **输出** : {1: 7，4: 3，6: 10，3: 14}
> **解释**:不言自明的列式配对。

**方法#1:使用循环**

这是执行这项任务的方法之一。在这种情况下，我们迭代所有元素及其下一列元素，并构造字典键值对。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Column Mapped Tuples to dictionary items
# Using loop

# initializing list
test_list = [[(5, 6), (7, 4), (1, 2)], 
             [(7, 3), (10, 14), (11, 22)] ]

# printing original list
print("The original list : " + str(test_list))

res = dict()

# loop for tuple lists
for idx in range(len(test_list) - 1):
    for idx2 in range(len(test_list[idx])):

        # column wise dictionary pairing 
        res[test_list[idx][idx2][0]] = test_list[idx + 1][idx2][0]
        res[test_list[idx][idx2][1]] = test_list[idx + 1][idx2][1]

# printing result 
print("The constructed dictionary : " + str(res))
```

**Output**

> 原始列表:[(5，6)，(7，4)，(1，2)]，[(7，3)，(10，14)，(11，22)]
> 构造的字典:{5: 7，6: 3，7: 10，4: 14，1: 11，2: 22}

**方法 2:使用词典理解+ zip()**

上述功能的结合提供了一个解决这个问题的方法。在本例中，我们使用 zip()执行压缩所有列的任务，字典理解用于键值对。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Column Mapped Tuples to dictionary items
# Using dictionary comprehension + zip()

# initializing list
test_list = [[(5, 6), (7, 4), (1, 2)], 
             [(7, 3), (10, 14), (11, 22)] ]

# printing original list
print("The original list : " + str(test_list))

# nested dictionary comprehension to form pairing 
# paired using zip()
res = {key[idx] : val[idx] for key, val in zip(
         *tuple(test_list)) for idx in range(len(key))}

# printing result 
print("The constructed dictionary : " + str(res))
```

**Output**

> 原始列表:[(5，6)，(7，4)，(1，2)]，[(7，3)，(10，14)，(11，22)]
> 构造的字典:{5: 7，6: 3，7: 10，4: 14，1: 11，2: 22}