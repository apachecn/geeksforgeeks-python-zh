# Python–检查列表是否 K 增加

> 原文:[https://www . geesforgeks . org/python-check-if-list-is-k-递增/](https://www.geeksforgeeks.org/python-check-if-list-is-k-increasing/)

给定一个列表，检查下一个元素是否总是比当前元素(x)大 x + K。

> **输入** : test_list = [3，7，11，15，19，23]，K = 4
> **输出** : True
> **解释**:后续元素差为 4。
> 
> **输入** : test_list = [3，7，11，12，19，23]，K = 4
> **输出** : False
> **解释**:12–11 = 1，不是 4，因此为 False

**方法#1:使用循环**

在这种情况下，我们对列表的每个元素进行迭代，并检查元素是否没有增加 K，如果找到，结果被标记为假并返回。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Check if List is K increasing
# Using loop

# initializing list
test_list = [4, 7, 10, 13, 16, 19]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3 

res = True 
for idx in range(len(test_list) - 1):

    # flagging if not found
    if test_list[idx + 1] != test_list[idx] + K:
        res = False

# printing results
print("Is list K increasing ? : " + str(res))
```

**Output**

```py
The original list is : [4, 7, 10, 13, 16, 19]
Is list K increasing ? : True

```

**方法 2:使用 all() +生成器表达式**

在这种情况下，我们使用 all()检查所有元素是否为 K 递增，并使用生成器表达式进行迭代。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Check if List is K increasing
# Using all() + generator expression

# initializing list
test_list = [4, 7, 10, 13, 16, 19]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 3 

# using all() to check for all elements
res = all(test_list[idx + 1] == test_list[idx] + K for idx in range(len(test_list) - 1))

# printing results
print("Is list K increasing ? : " + str(res))
```

**Output**

```py
The original list is : [4, 7, 10, 13, 16, 19]
Is list K increasing ? : True

```