# Python–将字符串真值转换为布尔值

> 原文:[https://www . geesforgeks . org/python-convert-string-true-values-to-boolean/](https://www.geeksforgeeks.org/python-convert-string-truth-values-to-boolean/)

给定字符串列表，将字符串真值转换为布尔值。

> **输入** : test_list = [“真”、“假”、“真”、“假”]
> **输出**:【真、假、真、假】
> **解释**:字符串布尔值转换为实际布尔值。
> 
> **输入**:test _ list =[“True”]
> **输出**:【True】
> **解释**:字符串布尔转换为实际布尔。

**方法一:使用列表理解**

在这种情况下，我们只检查真值，其余值自动转换为假布尔值。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert String Truth values to Boolean
# Using list comprehension

# initializing lists
test_list = ["True", "False", "True", "True", "False"]

# printing string
print("The original list : " + str(test_list))

# using list comprehension to check "True" string
res = [ele == "True" for ele in test_list]

# printing results 
print("The converted Boolean values : " + str(res))
```

**Output**

```
The original list : ['True', 'False', 'True', 'True', 'False']
The converted Boolean values : [True, False, True, True, False]

```

**方法 2:使用 map() + lambda**

在这方面，我们采用相同的方法，只是解决问题的方式不同。map()用于扩展 lambda 函数计算值的逻辑。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Convert String Truth values to Boolean
# Using map() + lambda

# initializing lists
test_list = ["True", "False", "True", "True", "False"]

# printing string
print("The original list : " + str(test_list))

# using map() to extend and lambda to check "True" string
res = list(map(lambda ele: ele == "True", test_list))

# printing results 
print("The converted Boolean values : " + str(res))
```

**Output**

```
The original list : ['True', 'False', 'True', 'True', 'False']
The converted Boolean values : [True, False, True, True, False]

```