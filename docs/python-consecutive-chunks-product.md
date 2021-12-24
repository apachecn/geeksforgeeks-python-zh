# Python |连续组块产品

> 原文:[https://www . geesforgeks . org/python-continuous-chunks-product/](https://www.geeksforgeeks.org/python-consecutive-chunks-product/)

编程领域的一些经典问题来自不同的类别，其中之一就是寻找子集的乘积。当我们需要计算产品并存储连续的组产品价值时，这个特殊的问题也很常见。让我们用 python 语言尝试不同的方法来解决这个问题。

**方法#1:使用列表理解+循环**
可以使用列表理解来执行这个特定的任务，以过滤出连续的组，并且可以使用乘积显式函数来获得过滤后的解的乘积。

```
# Python3 code to demonstrate
# Consecutive chunks Product
# using list comprehension + loop

# getting Product
def prod(val) :
    res = 1 
    for ele in val:
        res *= ele
    return res 

# initializing list
test_list = [4, 7, 8, 10, 12, 15, 13, 17, 14]

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + loop
# Consecutive chunks Product
res = [ prod(test_list[x : x + 3]) for x in range(0, len(test_list), 3)]

# printing result
print("The chunked product list is : " + str(res))
```

**Output :**

```
The original list : [4, 7, 8, 10, 12, 15, 13, 17, 14]
The chunked product list is : [224, 1800, 3094]

```