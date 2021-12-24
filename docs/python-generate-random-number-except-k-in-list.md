# Python |生成列表中除 K 以外的随机数

> 原文:[https://www . geesforgeks . org/python-generate-random-number-except-k-in-list/](https://www.geeksforgeeks.org/python-generate-random-number-except-k-in-list/)

有时候，在使用 python 时，我们可能会遇到一个问题，需要生成随机数。这看起来很容易，但有时我们需要对其稍加修改。也就是说，我们需要从 k 以外的列表中生成随机数。让我们讨论执行该任务的某些方式。

**方法一:使用`choice()` +列表理解**
以上功能的组合可以用来执行此任务。在这种情况下，我们首先使用列表理解过滤掉除 K 之外的数字，然后将该列表馈送给 choice()以生成随机数。

```
# Python3 code to demonstrate 
# Generate random number except K in list
# using choice() + list comprehension
import random

# Initializing list 
test_list = [4, 7, 8, 4, 6, 10]

# printing original list
print("The original list is : " + str(test_list))

# Initializing K 
K = 4

# Generate random number except K in list
# using choice() + list comprehension
res = random.choice([ele for ele in test_list if ele != K])

# printing result 
print ("The random number except K is : " + str(res))
```

**Output :**

```
The original list is : [4, 7, 8, 4, 6, 10]
The random number except K is : 8

```