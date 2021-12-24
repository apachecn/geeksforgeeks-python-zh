# Python–检查元组中是否存在任何列表元素

> 原文:[https://www . geeksforgeeks . org/python-如果有检查列表元素存在于元组中/](https://www.geeksforgeeks.org/python-check-if-any-list-element-is-present-in-tuple/)

给定一个元组，检查其中是否存在任何列表元素。

> **输入** : test_tup = (4，5，10，9，3)，check_list = [6，7，10，11]
> **输出** : True
> **解释** : 10 同时出现在元组和列表中。
> 
> **输入** : test_tup = (4，5，12，9，3)，check_list = [6，7，10，11]
> **输出** : False
> **解释**:无共同元素。

**方法#1:使用循环**

在这种情况下，我们保留一个布尔变量，保存所有元素的记录，如果找到，则返回真，否则返回假。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Check if any list element is present in Tuple
# Using loop

# initializing tuple
test_tup = (4, 5, 7, 9, 3)

# printing original tuple
print("The original tuple is : " + str(test_tup))

# initializing list
check_list = [6, 7, 10, 11]

res = False
for ele in check_list:

    # checking using in operator
    if ele in test_tup :
        res = True
        break

# printing result
print("Is any list element present in tuple ? : " + str(res))
```

**Output**

```
The original tuple is : (4, 5, 7, 9, 3)
Is any list element present in tuple ? : True
```

**方法 2:使用任意()**

如果在元组中找到列表的任何元素，则返回真，使用 in 运算符进行测试。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Check if any list element is present in Tuple
# Using any()

# initializing tuple
test_tup = (4, 5, 7, 9, 3)

# printing original tuple
print("The original tuple is : " + str(test_tup))

# initializing list
check_list = [6, 7, 10, 11]

# generator expression is used for iteration
res = any(ele in test_tup for ele in check_list)

# printing result
print("Is any list element present in tuple ? : " + str(res))
```

**Output**

```
The original tuple is : (4, 5, 7, 9, 3)
Is any list element present in tuple ? : True
```