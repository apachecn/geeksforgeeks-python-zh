# Python–检查矩阵行中的相似元素

> 原文:[https://www . geesforgeks . org/python-check-相似-矩阵中的元素-行/](https://www.geeksforgeeks.org/python-check-similar-elements-in-matrix-rows/)

给定一个矩阵和列表，任务是编写一个 Python 程序来检查该行的所有矩阵元素是否与列表的第 i <sup>个</sup>索引相似。

> **输入** : test_list = [[1，1，1]，[4，4]，[3，3，3]，[5，5，5，5]]
> **输出** : True
> **解释**:所有行都有相同的元素。
> 
> **输入** : test_list = [[1，1，4]，[4，4]，[3，3，3]，[5，5，5，5]]
> **输出** : False
> **解释**:所有行没有相同的元素。

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/)

在这种情况下，我们遍历每一行并检查它在列表中的相似编号，如果一行中的所有元素都与列表中的第 i <sup>个</sup>元素相同，则返回 true，否则返回 false。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Similar all elements as List in Matrix rows
# Using loop

# initializing Matrix
test_list = [[1, 1, 1], [4, 4],
             [3, 3, 3], [5, 5, 5, 5]]

# printing original list
print("The original list is : " + str(test_list))

# initializing tar_list 
tar_list = [1, 4, 3, 5]

res = True
flag = 0
for idx in range(len(test_list)):
    for ele in test_list[idx]:

        # checking for row index 
        # equal to list index elements 
        if ele != tar_list[idx]:
            res = False 
            flag = 1
            break

    if flag:
        break

# printing result
print("Are row index element similar\
       to list index element ? : " + str(res))
```

**输出:**

> 原来的列表是:[[1，1，1]，[4，4]，[3，3，3]，[5，5，5，5]]
> 行索引元素和列表索引元素相似吗？:真

**方法 2:使用 all() +** [**生成器表达式**](https://www.geeksforgeeks.org/generator-expressions/)

在这种情况下，我们使用 all()检查所有元素是否相等，并再次使用 all()检查遵循此模式的所有元素。元素和行的迭代是使用生成器表达式完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Similar all elements as List in Matrix rows
# Using all() + generator expression

# initializing Matrix
test_list = [[1, 1, 1], [4, 4],
             [3, 3, 3], [5, 5, 5, 5]]

# printing original list
print("The original list is : " + str(test_list))

# initializing tar_list 
tar_list = [1, 4, 3, 5]

# nested all() used to check each element and rows
res = all(all(ele == tar_list[idx] for ele in test_list[idx])
          for idx in range(len(test_list)) )

# printing result
print("Are row index element\
    similar to list index element ? : " + str(res))
```

**输出:**

> 原来的列表是:[[1，1，1]，[4，4]，[3，3，3]，[5，5，5，5]]
> 行索引元素和列表索引元素相似吗？:真