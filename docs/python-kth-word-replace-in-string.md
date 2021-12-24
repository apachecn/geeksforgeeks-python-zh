# Python–字符串中的第 Kth 个单词替换

> 原文:[https://www . geesforgeks . org/python-kth-word-replace-in-string/](https://www.geeksforgeeks.org/python-kth-word-replace-in-string/)

有时，在处理字符串列表时，我们会遇到一个问题，即需要替换字符串中最多的第 Kt 个单词。这个问题在 web 开发领域有很多应用。让我们讨论一下解决这个问题的方法。

**方法:使用`split() + join()`**
这是我们执行这个任务的方式。在这种情况下，我们将元素分成几部分，然后返回 Kth 值，并使用 join()执行新元素的添加。

```py
# Python3 code to demonstrate working of
# Kth word replace in String
# using split() + join()

# initializing string 
test_str = "GFG is good"

# printing original string 
print("The original string is : " + test_str)

# initializing replace string 
rep_str = "best"

# initializing K 
K = 1 

# Kth word replace in String
# using split() + join()
temp = test_str.split(' ')
res = " ".join(temp[: K]  + [rep_str] + temp[K + 1 :])

# printing result
print("The String after performing replace : " + res)
```

**Output :**

```py
The original string is : GFG is good
The String after performing replace : GFG best good

```