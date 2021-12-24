# Python–求指数值的乘积，求总和

> 原文:[https://www . geesforgeks . org/python-查找索引值的乘积并查找总和/](https://www.geeksforgeeks.org/python-find-product-of-index-value-and-find-the-summation/)

给定一个元素列表，编写一个 Python 程序来执行索引和值的乘积并计算总和。

**示例:**

> **输入** : test_list = [5，3，4，9，1，2]
> **输出** : 76
> **解释** : 5 + (3*2) 6 + 12 + 36 + 5 + 12 = 76
> 
> **输入**:test _ list =【5，3，4】
> **输出** : 23
> **解释** : 5 + (3*2) 6 + 12 = 23

**方法#1:使用 loop +** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/)

在本文中，我们使用 enumerate()对每个元素及其索引进行迭代，并计算乘积。Sum 计数器用于更新计算出的乘积的中间和。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Index Value Product Sum
# Using loop + enumerate()

# initializing list
test_list = [5, 3, 4, 9, 1, 2]

# printing original list
print("The original list is : " + str(test_list))

res = 0
for idx, ele in enumerate(test_list):

    # updating summation of required product
    res += (idx + 1) * ele

# printing result
print("The computed sum : " + str(res))
```

**Output**

```
The original list is : [5, 3, 4, 9, 1, 2]
The computed sum : 76
```

**方法二:使用** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+** [**枚举()**](https://www.geeksforgeeks.org/enumerate-in-python/)

解决这个问题的一种线性方法是，在这个方法中，我们执行获取产品迭代的任务，因为列表理解和最后的求和是使用 sum()完成的。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Index Value Product Sum
# Using loop + enumerate()

# initializing list
test_list = [5, 3, 4, 9, 1, 2]

# printing original list
print("The original list is : " + str(test_list))

# one liner to solve problem using list comprehension
res = sum([(idx + 1) * ele for idx, ele in enumerate(test_list)])

# printing result
print("The computed sum : " + str(res))
```

**Output**

```
The original list is : [5, 3, 4, 9, 1, 2]
The computed sum : 76
```