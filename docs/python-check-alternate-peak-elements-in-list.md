# Python–检查列表

中的替代峰值元素

> 原文:[https://www . geesforgeks . org/python-check-alternate-peak-elements-in-list/](https://www.geeksforgeeks.org/python-check-alternate-peak-elements-in-list/)

给定一个列表，任务是编写一个 Python 程序来测试它是否是交替的，即下一个和上一个元素在整个列表中是更小还是更大。

> **输入** : test_list = [2，4，1，6，4，8，0]
> **输出** : True
> **解释** : 4，6，8 为交替和峰值(2 ^ 1)。
> 
> **输入** : test_list = [2，4，1，6，4，1，0]
> **输出** : False
> **说明** : 1 不是峰值(4 < 1 < 0)。

**方法#1:使用** [**循环**](https://www.geeksforgeeks.org/loops-in-python/) **。**

在这种情况下，我们使用条件 if 语句检查每个元素的下一个和上一个元素是更小还是更大，如果发现任何变化，结果被标记为 false 并退出循环。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test for alternate peak List
# Using loop

# initializing list
test_list = [2, 4, 1, 6, 4, 8, 0]

# printing original list
print("The original list is : " + str(test_list))

res = True 
for idx in range(1, len(test_list) - 1):

    # breaking if not alternate peaks
    if not ((test_list[idx - 1] < test_list[idx] 
             and test_list[idx + 1] < test_list[idx])
            or (test_list[idx - 1] > test_list[idx] 
                and test_list[idx + 1] > test_list[idx])):

        res = False

# printing result
print("Is list forming alternate peaks ? : " + str(res))
```

**输出:**

```
The original list is : [2, 4, 1, 6, 4, 8, 0]
Is list forming alternate peaks ? : True
```

**方法 2:使用**[**all()**](https://www.geeksforgeeks.org/any-all-in-python/)**+**[**发生器表达式**](https://www.geeksforgeeks.org/generator-expressions/) **。**

在本例中，我们使用 all()执行检查所有元素以获得交替峰值的任务，生成器表达式用于迭代整个列表。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Test for alternate peak List
# Using all() + generator expression

# initializing list
test_list = [2, 4, 1, 6, 4, 8, 0]

# printing original list
print("The original list is : " + str(test_list))

# checking for all the elements for alternate peaks 
# one liner solution to problem
res = all(((test_list[idx - 1] < test_list[idx]
            and test_list[idx + 1] < test_list[idx]) 
           or (test_list[idx - 1] > test_list[idx] 
               and test_list[idx + 1] > test_list[idx]))
          for idx in range(1, len(test_list) - 1))

# printing result
print("Is list forming alternate peaks ? : " + str(res))
```

**输出:**

```
The original list is : [2, 4, 1, 6, 4, 8, 0]
Is list forming alternate peaks ? : True
```