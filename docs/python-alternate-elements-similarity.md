# Python–替代元素相似性

> 原文:[https://www . geesforgeks . org/python-alternative-elements-相似性/](https://www.geeksforgeeks.org/python-alternate-elements-similarity/)

给定元素列表，检查所有替换元素是否等于 k

> **输入** : test_list = [5，3，5，2，5，8，9]，K = 5
> **输出** : False
> **解释** : 9！= 5，因此为假。
> 
> **输入** : test_list = [4，3，4，2，4]，K = 4
> **输出** : True
> **解释**:所有候补等于 4。

**方法#1:使用循环**

这是解决这个问题的粗暴方法。在这种情况下，迭代列表中的每个元素，并检查每个元素是否等于 k。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Alternate elements Similarity
# Using loop

# initializing lists
test_list = [5, 3, 5, 2, 5, 8, 5]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 5

# using flag to Flag false if any one element is not K 
# using loop to check for each element
res = True
for idx, ele in enumerate(test_list):
    if not idx % 2 and ele != K: 
        res = False 
        break

# printing result 
print("Are all alternate elements equal to K : " + str(res))
```

**Output**

```py
The original list : [5, 3, 5, 2, 5, 8, 5]
Are all alternate elements equal to K : True

```

**方法 2:使用 all() +生成器表达式**

这是执行这项任务的另一种方式。在本例中，我们使用 all()检查所有元素，生成器表达式用于条件检查和迭代。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Alternate elements Similarity
# Using all() + generator expression

# initializing lists
test_list = [5, 3, 5, 2, 5, 8, 5]

# printing original list
print("The original list : " + str(test_list))

# initializing K 
K = 5

# all() to encapsulate whole logic into one expression
res = all(test_list[idx] == K for idx in range(0, len(test_list), 2))

# printing result 
print("Are all alternate elements equal to K : " + str(res))
```

**Output**

```py
The original list : [5, 3, 5, 2, 5, 8, 5]
Are all alternate elements equal to K : True

```