# Python–二元组交替求和

> 原文:[https://www . geesforgeks . org/python-二元组-交替-求和/](https://www.geeksforgeeks.org/python-dual-tuple-alternate-summation/)

给定二元组，执行交替元素的求和，即交替的索引。

> **输入** : test_list = [(4，1)，(5，6)，(3，5)，(7，5)]
> **输出** : 18
> **解释** : 4 + 6 + 3 + 5 = 18，交替相加求和。
> 
> **输入** : test_list = [(4，1)，(5，6)，(3，5)]
> **输出** : 13
> **解释** : 4 + 6 + 3 = 183，交替相加。

**方法#1:使用循环**

在这种情况下，我们遍历每个元组，并检查列表中的索引，如果是偶数，则元组的第一个元素被求和，否则第二个元素被添加到计算的和中。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Dual Tuple Alternate summation
# Using loop

# initializing list
test_list = [(4, 1), (5, 6), (3, 5), (7, 5), (1, 10)]

# printing original list
print("The original list is : " + str(test_list))

res = 0
for idx in range(len(test_list)):

    # checking for Alternate element
    if idx % 2 == 0:
        res += test_list[idx][0]
    else:
        res += test_list[idx][1]

# printing result
print("Summation of Alternate elements of tuples : " + str(res))
```

**Output**

```py
The original list is : [(4, 1), (5, 6), (3, 5), (7, 5), (1, 10)]
Summation of Alternate elements of tuples : 19

```

**方法 2:使用列表理解+求和()**

在本例中，我们使用 *sum()* 执行求和任务，列表理解用于为列表中元组的迭代提供紧凑的解决方案。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Dual Tuple Alternate summation
# Using list comprehension + sum()

# initializing list
test_list = [(4, 1), (5, 6), (3, 5), (7, 5), (1, 10)]

# printing original list
print("The original list is : " + str(test_list))

# summation using sum(), list comprehension offers shorthand
res = sum([test_list[idx][0] if idx % 2 == 0 else test_list[idx][1] for idx in range(len(test_list))])

# printing result 
print("Summation of Alternate elements of tuples : " + str(res))
```

**Output**

```py
The original list is : [(4, 1), (5, 6), (3, 5), (7, 5), (1, 10)]
Summation of Alternate elements of tuples : 19

```