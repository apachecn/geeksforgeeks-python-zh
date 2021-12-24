# Python |匹配 I，j 索引元素的计数

> 原文:[https://www . geesforgeks . org/python-匹配计数-i-j-index-elements/](https://www.geeksforgeeks.org/python-count-of-matching-i-j-index-elements/)

有时，在编程时，我们会遇到一个问题，需要检查每个字符串的第 I 个和第 jth 个字符。我们可能需要提取具有相似 ith 和 jth 字符的所有字符串的计数。让我们讨论执行这项任务的某些方法。

**方法#1:使用循环**
这是可以执行该任务的蛮力方法。在这种情况下，迭代列表的每个元素，检查每个字符串的 ith 和 jth 字符，并增加计数器，以防我们发现匹配。

```
# Python3 code to demonstrate working of
# Count of Matching i, j index elements
# Using loop

# initialize list 
test_list = ['geeks', 'beke', 'treat', 'neke']

# printing original list 
print("The original list : " + str(test_list))

# initialize i 
i = 1

# initialize j 
j = 3 

# Count of Matching i, j index elements
# Using loop
count = 0
for ele in test_list:
    if ele[i] == ele[j]:
        count = count + 1

# printing result
print("Total Strings with similar ith and jth elements : " + str(count))
```

**Output :**

```
The original list : ['geeks', 'beke', 'treat', 'neke']
Total Strings with similar ith and jth elements : 2

```