# Python |如何将元组连接成嵌套元组

> 原文:[https://www . geesforgeks . org/python-如何将元组连接到嵌套元组/](https://www.geeksforgeeks.org/python-how-to-concatenate-tuples-to-nested-tuples/)

有时，在使用元组时，我们可能会遇到一个问题，即我们需要将单个记录转换为嵌套集合，但仍然作为单独的元素。元组的通常添加，通常会添加内容，从而使结果容器变平，这通常是不希望的。让我们讨论解决这个问题的某些方法。

**方法#1:在初始化**
时使用`+ operator` + `", " operator` 在这个方法中，我们执行元组元素的通常添加，但是在初始化元组时，我们在元组后添加逗号，这样它们在添加时不会变平。

```
# Python3 code to demonstrate working of
# Concatenating tuples to nested tuples
# using + operator + ", " operator during initialization

# initialize tuples
test_tup1 = (3, 4),
test_tup2 = (5, 6),

# printing original tuples
print("The original tuple 1 : " + str(test_tup1))
print("The original tuple 2 : " + str(test_tup2))

# Concatenating tuples to nested tuples
# using + operator + ", " operator during initialization
res = test_tup1 + test_tup2

# printing result
print("Tuples after Concatenating : " + str(res))
```

**Output :**

```
The original tuple 1 : ((3, 4), )
The original tuple 2 : ((5, 6), )
Tuples after Concatenating : ((3, 4), (5, 6))

```