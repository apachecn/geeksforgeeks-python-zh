# Python–提取等对字典

> 原文:[https://www . geesforgeks . org/python-extract-equal-pair-dictionary/](https://www.geeksforgeeks.org/python-extract-equal-pair-dictionary/)

有时，在使用 Python 字典时，我们可能会遇到这样的问题，即需要在现有字典的基础上创建一个新字典，以元组为关键字。我们希望只在配对的两个元素相等的情况下创建带有键的 singlton 键字典。这在许多领域都有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是一种可以执行该任务的暴力方式。在这种情况下，我们对元组字典的每个元素进行迭代，并比较是否相等，以创建新的字典。

```
# Python3 code to demonstrate working of 
# Extract Equal Pair Dictionary 
# Using loop

# initializing dictionary
test_dict = { (1, 1) : 4, (2, 3) : 6, (3, 3) : 7, (5, 2) : 10, (2, 2) : 11}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Extract Equal Pair Dictionary 
# Using loops
res = dict()
for key, val in test_dict.items():
    if key[0] == key[1]:
        res[key[0]] = val

# printing result 
print("The dictionary after equality testing : " + str(res)) 
```

**Output :**

> 原字典为:{(5，2): 10，(2，2): 11，(2，3): 6，(1，1): 4，(3，3): 7}
> 等式测试后的字典:{1: 4，2: 11，3: 7}