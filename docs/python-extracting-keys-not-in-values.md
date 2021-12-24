# Python–提取不在值中的键

> 原文:[https://www . geesforgeks . org/python-提取键-不在值中/](https://www.geeksforgeeks.org/python-extracting-keys-not-in-values/)

有时，在使用 Python 字典时，我们可能会遇到一个问题，即我们需要获取值列表中没有出现的所有键。这可以在日常编程等领域得到应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用`set() + values() + keys()` +循环**
这是一种蛮力的方式来接近这个任务。在这种情况下，我们测试值列表中的元素，并在单独的列表中不断添加它们。然后我们使用 key()从提取的密钥中减去这个值。

```
# Python3 code to demonstrate working of 
# Extracting keys not in values
# Using set() + keys() + values() + loop

# initializing Dictionary
test_dict = {3 : [1, 3, 4], 5 : [1, 2], 6 : [4, 3], 4 : [1, 3]}

# printing original dictionary
print("The original dictionary is : " + str(test_dict))

# Extracting keys not in values
# Using set() + keys() + values() + loop
temp1 = set(test_dict.keys())
temp2 = set()
for ele in test_dict.values():
    temp2.update(ele)
res = list(temp1 - temp2)

# printing result 
print("The extracted keys are : " + str(res)) 
```

**Output :**

> 原始字典为:{3: [1，3，4]，4: [1，3]，5: [1，2]，6: [4，3]}
> 提取的键为:[5，6]