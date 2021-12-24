# Python–Lambda 函数查找两个元素之间的较小值

> 原文:[https://www . geesforgeks . org/python-lambda-function-to-find-两个元素之间的较小值/](https://www.geeksforgeeks.org/python-lambda-function-to-find-the-smaller-value-between-two-elements/)

[λ函数](https://www.geeksforgeeks.org/python-lambda-anonymous-functions-filter-map-reduce/)是一个匿名函数。它可以有任意数量的参数，但只能有一个表达式。

> **语法**λ参数:表达式

在本文中，我们将学习如何使用 Lambda 函数找到两个元素之间的较小值。

**例:**

```
Input : 2 5
Output : 2

Input : 7 5
Output : 5
```

### **方法 1:** 使用λ和 [min()](https://www.geeksforgeeks.org/max-min-python/) 方法

## 蟒蛇 3

```
# lambda function to return minimum of
# two elements a, b are the arguments and
# min() method is the expression here.
get_min = lambda a, b : min(a,b)

print(get_min(5, 8))
```

**输出:**

```
5
```

**说明:**a、b 传递给 lambda 函数，min()方法作为表达式返回最小元素。

### **方法二:**使用λ和[三元算子](https://www.geeksforgeeks.org/ternary-operator-in-python/)

## 蟒蛇 3

```
# lambda function to return minimum of two elements
# a, b are the arguments and ternary
# operator is used to compare two elements
get_min = lambda a, b : a if a < b else b

print(get_min(5, 8))
```

**输出:**

```
5
```

**说明:** a、b 为自变量，三元运算符用于比较两个元素

### **方法 3 :** 使用[元组](https://www.geeksforgeeks.org/python-tuples/)和λ

## 蟒蛇 3

```
# Two lambda functions will be stored
# in tuple such that 1st element is b
# and 2nd element will be b.
# if [a<b] is true it return 1 and
# element with index 1 will print
# else if [a<b] is false it return 0,
# so element with index 0 will print
a = 5
b = 8
print((lambda: b, lambda: a)[a < b]())
```

**输出:**

```
5
```

**说明:**

两个 lambda 函数将存储在一个元组中，这样第一个元素是 b，第二个元素是 b，如果[a