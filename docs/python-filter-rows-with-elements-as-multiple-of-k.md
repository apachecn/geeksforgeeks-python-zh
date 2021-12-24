# Python–过滤元素为 K 倍数的行

> 原文:[https://www . geesforgeks . org/python-filter-rows-with-elements-as-multiple-of-k/](https://www.geeksforgeeks.org/python-filter-rows-with-elements-as-multiple-of-k/)

给定一个矩阵，提取 k 元素倍数的行。

> **输入** : test_list = [[5，10，15]，[4，8，12]，[100，15]，[5，10，23]]，K = 4
> **输出** : [[4，8，12]]
> **解释**:均为 4 的倍数。
> 
> **输入** : test_list = [[5，10，15]，[4，8，11]，[100，15]，[5，10，23]]，K = 4
> **输出** : []
> **解释**:无所有 4 倍数的行。

**方法一:使用列表理解+ all()**

在本例中，我们使用 all()检查所有元素是否为多个，并使用列表理解进行行迭代。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Access element at Kth index in String
# Using list comprehension + all()

# initializing string list
test_list = [[5, 10, 15], [4, 8, 3], [100, 15], [5, 10, 23]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 5

res = [sub for sub in test_list if all(ele % K == 0 for ele in sub)]

# printing result
print("Rows with K multiples : " + str(res))
```

**Output**

> 原列表为:[[5，10，15]，[4，8，3]，[100，15]，[5，10，23]]
> K 倍数行:[[5，10，15]，[100，15]]

**方法 2:使用滤镜()+ lambda + all()**

在本例中，我们使用 filter()和 lambda 函数执行过滤任务，并使用 all()执行检查行中所有元素的任务。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Access element at Kth index in String
# Using filter() + lambda + all()

# initializing string list
test_list = [[5, 10, 15], [4, 8, 3], [100, 15], [5, 10, 23]]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 5

# using all() to check for all elements being multiples of K
res = list(filter(lambda sub : all(ele % K == 0 for ele in sub), test_list))

# printing result 
print("Rows with K multiples : " + str(res))
```

**Output**

> 原列表为:[[5，10，15]，[4，8，3]，[100，15]，[5，10，23]]
> K 倍数行:[[5，10，15]，[100，15]]