# Python–计算列表中正元素的百分比

> 原文:[https://www . geesforgeks . org/python-计算列表中正元素的百分比/](https://www.geeksforgeeks.org/python-calculate-the-percentage-of-positive-elements-of-the-list/)

给定一个列表，计算列表中正元素的百分比。

> **输入** : test_list = [4，6，-2，3，-8，-9，-1，8，9，1]
> **输出** : 60.0
> **解释** : 6/10 元素为正。
> 
> **输入** : test_list = [-4，6，-2，3，-8，-9，-1，8，9，1]
> **输出** : 50.0
> **解释** : 5/10 元素为正。

**方法#1:使用**[**len()**](https://www.geeksforgeeks.org/python-string-length-len/)**+**[**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension-and-slicing/)

在这种情况下，我们使用列表理解构造正元素列表，然后使用 len()计算列表的长度，两个长度除以 100，得到百分比计数。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Positive values percentage 
# Using len() + list comprehension

# initializing list
test_list = [4, 6, -2, 3, -8, 0, -1, 8, 9, 1]

# printing original list
print("The original list is : " + str(test_list))

# getting filtered list using comprehension and 
# division to get fraction
res = (len([ele for ele in test_list if ele > 0]) / len(test_list)) * 100

# printing result 
print("Positive elements percentage : " + str(res))
```

**输出:**

```
The original list is : [4, 6, -2, 3, -8, 0, -1, 8, 9, 1]
Positive elements percentage : 60.0
```

**方法 2:使用** [**滤镜()**](https://www.geeksforgeeks.org/filter-in-python/)**+**[**λ**](https://www.geeksforgeeks.org/python-lambda/)**+len()**

在本例中，我们使用 filter()和 lambda 执行获取正元素的任务，剩下的所有任务都类似于上述方法执行。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Positive values percentage
# Using filter() + lambda + len()

# initializing list
test_list = [4, 6, -2, 3, -8, 0, -1, 8, 9, 1]

# printing original list
print("The original list is : " + str(test_list))

# getting filtered list using filter(), lambda and
# division to get fraction
res = (len(list(filter(lambda ele: ele > 0, test_list))) / len(test_list)) * 100

# printing result
print("Positive elements percentage : " + str(res))
```

**输出:**

```
The original list is : [4, 6, -2, 3, -8, 0, -1, 8, 9, 1]
Positive elements percentage : 60.0
```