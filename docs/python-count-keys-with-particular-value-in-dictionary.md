# Python |统计字典中具有特定值的键

> 原文:[https://www . geesforgeks . org/python-count-key-with-special-value-in-dictionary/](https://www.geeksforgeeks.org/python-count-keys-with-particular-value-in-dictionary/)

有时候，在使用 Python 字典时，我们会遇到一个问题，在这个问题中，我们有一个特定的值，如果它出现了，我们需要找到它的频率。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用循环**
这个问题可以使用循环的天真方法来解决。在这种情况下，我们只需遍历字典中的每个键，当找到匹配项时，计数器就会增加。

```
# Python3 code to demonstrate working of
# Count keys with particular value in dictionary
# Using loop

# Initialize dictionary
test_dict = {'gfg' : 1, 'is' : 2, 'best' : 3, 'for' : 2, 'CS' : 2}

# printing original dictionary
print("The original dictionary : " +  str(test_dict))

# Initialize value 
K = 2

# Using loop
# Selective key values in dictionary
res = 0
for key in test_dict:
    if test_dict[key] == K:
        res = res + 1

# printing result 
print("Frequency of K is : " + str(res))
```

**Output :**

> 原词典:{'gfg': 1，' CS': 2，' best': 3，' for': 2，' is ':2 }
> K 的频率为:3