# Python–从其他键值中提取目标键

> 原文:[https://www . geesforgeks . org/python-extract-target-key-from-other-key-values/](https://www.geeksforgeeks.org/python-extract-target-key-from-other-key-values/)

有时，在使用 Python 字典时，我们会遇到一个问题，当存在精确匹配时，我们需要根据其他匹配的记录键提取特定的键。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环+条件**
这是可以执行该任务的方法之一。在这种情况下，我们迭代字典键，并检查每个键的匹配值。

```
# Python3 code to demonstrate working of 
# Extract target key from other key values
# Using loop + condition

# initializing list
test_list = [{ 'name' : 'Manjeet', 'English' : 14, 'Maths' : 2}, 
             { 'name' : 'Akshat', 'English' : 7, 'Maths' : 13},
             { 'name' : 'Akash', 'English' : 1, 'Maths' : 17},
             { 'name' : 'Nikhil', 'English' : 10, 'Maths' : 18}]

# printing original list
print("The original list is : " + str(test_list))

# initializing filter items 
filt_key = {'English' : 7, 'Maths' : 13}

# Extract target key from other key values
# Using loop + condition
res = []
for sub in test_list:
        if sub["English"] == filt_key["English"] and sub["Maths"] == filt_key["Maths"]:
            res.append(sub['name'])

# printing result 
print("The filtered result : " + str(res)) 
```

**Output :**

> 原始列表为:[{'name': 'Manjeet '，' English': 14，'数学':2}，{'name': 'Akshat '，' English': 7，'数学':13}，{'name': 'Akash '，' English': 1，'数学':17}，{'name': 'Nikhil '，' English': 10，'数学':18}]
> 筛选结果:['Akshat']