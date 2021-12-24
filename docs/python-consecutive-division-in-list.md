# Python–列表中的连续划分

> 原文:[https://www . geesforgeks . org/python-连续列表划分/](https://www.geeksforgeeks.org/python-consecutive-division-in-list/)

给定一个列表，对中间步骤中获得的每个商执行连续除法，并将连续元素视为除数。

> **输入**:test _ list =【1000，50，5，10，2】
> **输出** : 0.2
> **解释**:1000/50 = 20/5 = 4/10 = 0.4/2 = 0.2。因此解决方案。
> 
> **输入**:test _ list =【100，50】
> **输出** : 2
> **解释** : 100 / 50 = 2。因此解决方案。

**进场:使用循环+“/”运算符**

在这种情况下，我们对每个元素进行迭代，并将获得的商作为循环中下一个操作的被除数进行存储。最终结果是列表的最终商。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# Consecutive Division in List
# Using loop + / operator

# utility fnc.
def conc_div(test_list):

    res = test_list[0]
    for idx in range(1, len(test_list)):

        # Consecutive Division
        res /= test_list[idx]
    return res

# initializing list
test_list = [1000, 50, 5, 10, 2]

# printing original list
print("The original list is : " + str(test_list))

# getting conc. Division
res = conc_div(test_list)

# printing result 
print("The Consecutive Division quotient : " + str(res))
```

**Output**

```py
The original list is : [1000, 50, 5, 10, 2]
The Consecutive Division quotient : 0.2

```