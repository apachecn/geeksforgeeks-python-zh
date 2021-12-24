# Python–第 k 位数总和

> 原文:[https://www.geeksforgeeks.org/python-kth-digit-sum/](https://www.geeksforgeeks.org/python-kth-digit-sum/)

给定一个数字列表，提取第 k 个数字的总和。

> **输入**:test _ list =【5467，34232，45456，22222，3455】，K = 2
> **输出** : 19
> **解释** : 6 + 2 + 4 + 2 + 5 = 19。
> 
> **输入**:test _ list =【5467，34232，45456，22222，3455】，K = 0
> **输出** : 17
> **解释** : 5 + 3 + 4 + 2 + 3 = 17。

**方法#1:使用** [**str()**](https://www.geeksforgeeks.org/python-str-function/) **+循环**

在这种情况下，我们将元素转换为字符串，然后通过使用循环提取它来计算只有 Kth 个数字的总和。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Kth digit Sum
# Using loop + sum()

# initializing list
test_list = [5467, 34232, 45456, 22222, 3455]

# printing original list
print("The original list is : " + str(test_list))

# initializing K
K = 2

res = 0
for ele in test_list:

    # adding Kth digit
    res += int(str(ele)[K])

# printing result
print("Kth digit sum : " + str(res))
```

**输出:**

```
The original list is : [5467, 34232, 45456, 22222, 3455]
Kth digit sum : 19
```

**方法二:使用** [**求和()**](https://www.geeksforgeeks.org/sum-function-python/) **+** [**列表理解**](https://www.geeksforgeeks.org/python-list-comprehension/) **+ str()**

在这种情况下，我们使用 sum()执行得到 sum 的任务，并且使用列表理解来得到问题的单线方法。

## 蟒蛇 3

```
# Python3 code to demonstrate working of 
# Kth digit Sum 
# Using sum() + list comprehension + str()

# initializing list
test_list = [5467, 34232, 45456, 22222, 3455]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

# sum() getting summation
res = sum([int(str(ele)[K]) for ele in test_list])

# printing result 
print("Kth digit sum : " + str(res))
```

**输出:**

```
The original list is : [5467, 34232, 45456, 22222, 3455]
Kth digit sum : 19
```