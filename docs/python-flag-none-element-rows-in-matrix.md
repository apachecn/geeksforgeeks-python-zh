# Python–在矩阵中标记无元素行

> 原文:[https://www . geesforgeks . org/python-flag-none-element-row-in-matrix/](https://www.geeksforgeeks.org/python-flag-none-element-rows-in-matrix/)

给定矩阵，对于包含无值的行返回真，否则返回假。

> **输入** : test_list = [[2，4，无，3]，[3，4，1，无]，[2，4，7，4]，[2，8，无]]
> **输出**:【真，真，假，真】
> **解释** : 1，2，4 号索引不含出现。
> 
> **输入** : test_list = [[2，4，无，3]，[3，4，1，无]，[2，4，无，4]，[2，8，无]]
> **输出**:【真，真，真，真】
> **解释**:所有行无。

**方法一:使用列表理解**

在这种情况下，我们对每一行进行迭代，并使用 In 运算符检查这些行中的 None。如果找到，返回真，否则返回假。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Flag None Element Rows in Matrix
# Using list comprehension

# initializing list
test_list = [[2, 4, None, 3], [3, 4, 1, None], [2, 4, 7, 4], [2, 8]]

# printing original list
print("The original list is : " + str(test_list))

# in operator to check None value 
# True if any None is found 
res = [True if None in sub else False for sub in test_list]

# printing result 
print("None Flagged List : " + str(res))
```

**Output**

```
The original list is : [[2, 4, None, 3], [3, 4, 1, None], [2, 4, 7, 4], [2, 8]]
None Flagged List : [True, True, False, False]

```

**方法 2:使用 all() +列表理解**

在本例中，我们使用 all()检查所有值是否为真，如果是，则不标记为真，并使用列表理解来检查每一行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Flag None Element Rows in Matrix
# Using all() + list comprehension

# initializing list
test_list = [[2, 4, None, 3], [3, 4, 1, None], [2, 4, 7, 4], [2, 8]]

# printing original list
print("The original list is : " + str(test_list))

# all() checks for all non none values  
res = [False if all(sub) else True for sub in test_list]

# printing result 
print("None Flagged List : " + str(res))
```

**Output**

```
The original list is : [[2, 4, None, 3], [3, 4, 1, None], [2, 4, 7, 4], [2, 8]]
None Flagged List : [True, True, False, False]

```