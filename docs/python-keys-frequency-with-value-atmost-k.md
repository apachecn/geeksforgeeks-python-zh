# Python–键频率与值 K 的关系

> 原文:[https://www . geesforgeks . org/python-key-frequency-with-value-Atmos-k/](https://www.geeksforgeeks.org/python-keys-frequency-with-value-atmost-k/)

有时候，在使用 Python 字典时，我们会遇到一个问题，在这个问题中，我们有一个特定的值，如果它的出现频率和值是 atmost K，我们需要找到它。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环**
这个问题可以使用循环的天真方法来解决。在这种情况下，我们只需遍历字典中的每个键，当找到匹配项时，计数器就会增加。

```py
# Python3 code to demonstrate working of
# Keys Frequency with Value atmost K
# Using loop

# Initialize dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3, 'for' : 4, 'CS' : 5}

# printing original dictionary
print("The original dictionary : " + str(test_dict))

# Initialize value 
K = 3

# Using loop
# Keys Frequency with Value atmost K
res = 0
for key in test_dict:
    if test_dict[key] <= K:
        res = res + 1

# printing result 
print("Frequency of keys with values till K is : " + str(res))
```

**Output :**

```py
The original dictionary : {'CS': 5, 'is': 2, 'gfg': 1, 'best': 3, 'for': 4}
Frequency of keys with values till K is : 3

```