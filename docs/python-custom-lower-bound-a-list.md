# Python–自定义列表下限

> 原文:[https://www . geesforgeks . org/python-custom-下界-a-list/](https://www.geeksforgeeks.org/python-custom-lower-bound-a-list/)

给定一个列表，给它分配一个自定义的下界值。

> **输入** : test_list = [5，7，8，2，3，5，1]，K = 3
> **输出** : [5，7，8，3，3，5，3]
> **解释**:所有元素小于 3，赋 3。
> 
> **输入** : test_list = [5，7，8，2，3，5，1]，K = 5
> **输出** : [5，7，8，5，5，5，5]
> **解释**:所有元素小于 5，赋 5。

**方法一:使用** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们检查每个元素是否低于下限，如果是，则将确定的下限分配给该元素。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Custom Lowerbound a List
# Using list comprehension

# initializing list
test_list = [5, 7, 8, 2, 3, 5, 1]

# printing original list
print("The original list is : " + str(test_list))

# initializing Lowerbound
K = 4 

# checking for elements and assigning Lowerbounds
res = [ele if ele >= K else K for ele in test_list]

# printing result 
print("List with Lowerbounds : " + str(res))
```

**Output**

```
The original list is : [5, 7, 8, 2, 3, 5, 1]
List with Lowerbounds : [5, 7, 8, 4, 4, 5, 4]

```

**方法 2:使用列表理解+** [**max()**](https://www.geeksforgeeks.org/python-max-function/)

在这种情况下，我们使用 max()执行比较，根据决定分配元素的 max 或下限。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Custom Lowerbound a List
# Using list comprehension + max()

# initializing list
test_list = [5, 7, 8, 2, 3, 5, 1]

# printing original list
print("The original list is : " + str(test_list))

# initializing Lowerbound
K = 4 

# max() is used to compare for Lowerbound
res = [max(ele, K) for ele in test_list]

# printing result 
print("List with Lowerbounds : " + str(res))
```

**Output**

```
The original list is : [5, 7, 8, 2, 3, 5, 1]
List with Lowerbounds : [5, 7, 8, 4, 4, 5, 4]

```