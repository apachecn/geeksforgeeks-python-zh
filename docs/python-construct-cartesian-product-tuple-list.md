# Python |构建笛卡尔乘积元组列表

> 原文:[https://www . geesforgeks . org/python-construct-cartesian-product-tuple-list/](https://www.geeksforgeeks.org/python-construct-cartesian-product-tuple-list/)

有时，在处理数据时，我们需要创建数据作为所有可能的容器对。这种类型的应用程序来自 web 开发领域。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解**
这是执行这个特定任务的一种线性方式。在这种情况下，我们只需缩短一行中的循环任务，以生成所有可能的具有列表元素的元组对。

```py
# Python3 code to demonstrate working of
# Construct Cartesian Product Tuple list
# using list comprehension

# initialize list and tuple 
test_list = [1, 4, 6, 7]
test_tup = (1, 3)

# printing original list and tuple 
print("The original list : " + str(test_list))
print("The original tuple : " + str(test_tup))

# Construct Cartesian Product Tuple list
# using list comprehension
res = [(a, b) for a in test_tup for b in test_list]

# printing result
print("The Cartesian Product is : " + str(res))
```

**Output :**

> 原始列表:[1，4，6，7]
> 原始元组:(1，3)
> 笛卡尔积为:[(1，1)，(1，4)，(1，6)，(1，7)，(3，1)，(3，4)，(3，6)，(3，6)，(3，7)]