# Python–字符串中最少出现的字符

> 原文:[https://www . geesforgeks . org/python-最少出现的字符串字符/](https://www.geeksforgeeks.org/python-least-frequent-character-in-string/)

本文给出了找到 python 字符串中最小出现字符频率的方法。现在这是一个非常重要的工具，关于它的知识总是有用的。让我们讨论执行这项任务的某些方法。

**方法 1:天真方法+ `min()`**
在这个方法中，我们简单地遍历字符串，并在新出现的元素的字典中形成一个键，或者如果元素已经出现，我们将其值增加 1。我们通过在值上使用 min()找到最小出现字符。

```
# Python 3 code to demonstrate 
# Least Frequent Character in String
# naive method 

# initializing string 
test_str = "GeeksforGeeks"

# printing original string
print ("The original string is : " + test_str)

# using naive method to get
# Least Frequent Character in String
all_freq = {}
for i in test_str:
    if i in all_freq:
        all_freq[i] += 1
    else:
        all_freq[i] = 1
res = min(all_freq, key = all_freq.get) 

# printing result 
print ("The minimum of all characters in GeeksforGeeks is : " + str(res))
```

**Output :**

```
The original string is : GeeksforGeeks
The minimum of all characters in GeeksforGeeks is : f

```