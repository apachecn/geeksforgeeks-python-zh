# Python–检查所有元组的元素差异是否小于 K

> 原文:[https://www . geesforgeks . org/python-check-if-all-tuples-have-element-difference-小于-k/](https://www.geeksforgeeks.org/python-check-if-all-tuples-have-element-difference-less-than-k/)

给定一个元组列表，检查每个元组的差异是否小于 k

> **输入** : test_list = [(3，4)，(1，2)，(7，8)，(9，13)]，K = 2
> **输出** : False
> **解释**:13–9 = 4>2。
> 
> **输入** : test_list = [(3，4)，(1，2)，(7，8)]，K = 2
> **输出**:真
> **说明**:都有腹肌。diff 1 < 2。

**方法#1:使用循环**

在这种情况下，我们保留一个布尔变量，并检查是否有任何元素大于或等于 K，然后将其标记为 False 并断开。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Check if all tuples have element difference less than K
# Using loop

# initializing list
test_list = [(3, 4), (1, 2), (7, 8), (9, 8)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

res = True 
for ele1, ele2 in test_list:

    # using abs() to compute absolute difference
    if abs(ele1 - ele2) >= K:
        res = False 

# printing result 
print("Are all elements difference less than K ? : " + str(res))
```

**Output**

```py
The original list is : [(3, 4), (1, 2), (7, 8), (9, 8)]
Are all elements difference less than K ? : True

```

**方法 2:使用 all()**

在这种情况下，我们使用 all()来检查所有元组是否在 k 内有差异。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of 
# Check if all tuples have element difference less than K
# Using all()

# initializing list
test_list = [(3, 4), (1, 2), (7, 8), (9, 8)]

# printing original list
print("The original list is : " + str(test_list))

# initializing K 
K = 2

# shorthand to solve this problem
res = all(abs(sub1 - sub2) < K for sub1, sub2 in test_list)

# printing result 
print("Are all elements difference less than K ? : " + str(res))
```

**Output**

```py
The original list is : [(3, 4), (1, 2), (7, 8), (9, 8)]
Are all elements difference less than K ? : True

```