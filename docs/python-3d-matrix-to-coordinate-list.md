# Python-3D 矩阵转坐标列表

> 原文:[https://www . geesforgeks . org/python-3d-矩阵到坐标列表/](https://www.geeksforgeeks.org/python-3d-matrix-to-coordinate-list/)

给定一个矩阵，行的每个元素都是列表，对每个列形成坐标。

> **输入** : test_list = [[[9，2]，[10，3]]，[[13，6]，[19，7]]
> **输出** : [(9，10)，(2，3)，(13，19)，(6，7)]
> **解释**:列映射对。
> 
> **输入** : test_list = [[[13，6]，[19，7]]
> **输出** : [(13，19)，(6，7)]
> **解释**:列映射对。

**方法#1:使用 loop + zip()**

在这种情况下，我们迭代内部元组列表中的所有成对元素，该列表是使用 zip()成对的，并追加结果列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# 3D Matrix to Coordinate List
# Using loop + zip()

# initializing list
test_list = [[[5, 6, 7], [2, 4, 6]], [[9, 2], [10, 3]], [[13, 6], [19, 7]]]

# printing original list
print("The original list is : " + str(test_list))

res = []
for sub1, sub2 in test_list:

    # zip() used to form pairing
    for ele in zip(sub1, sub2):
        res.append(ele)

# printing result 
print("Constructed Pairs : " + str(res))
```

**Output**

```
The original list is : [[[5, 6, 7], [2, 4, 6]], [[9, 2], [10, 3]], [[13, 6], [19, 7]]]
Constructed Pairs : [(5, 2), (6, 4), (7, 6), (9, 10), (2, 3), (13, 19), (6, 7)]

```

**方法 2:使用列表理解**

在这篇文章中，我们使用列表理解来速记执行上述方法的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# 3D Matrix to Coordinate List
# Using loop + zip()

# initializing list
test_list = [[[5, 6, 7], [2, 4, 6]], [[9, 2], [10, 3]], [[13, 6], [19, 7]]]

# printing original list
print("The original list is : " + str(test_list))

# list comprehension to perform task in shorthand
res = [ele for sub1, sub2 in test_list for ele in zip(sub1, sub2)]

# printing result 
print("Constructed Pairs : " + str(res))
```

**Output**

```
The original list is : [[[5, 6, 7], [2, 4, 6]], [[9, 2], [10, 3]], [[13, 6], [19, 7]]]
Constructed Pairs : [(5, 2), (6, 4), (7, 6), (9, 10), (2, 3), (13, 19), (6, 7)]

```