# Python |列表中的 K 长度填充

> 原文:[https://www . geesforgeks . org/python-k-length-padding-in-list/](https://www.geeksforgeeks.org/python-k-length-padding-in-list/)

在现实问题中，我们有时需要根据达到最大字符数的条件填充列表元素。如果数字的长度小于任何字段的要求，则用 0 填充数字是 web 开发中 Web 表单中出现的基本问题之一。让我们讨论一下解决这个问题的某些方法。

**方法#1:使用列表理解**
这个问题可以使用基本的列表理解很容易地解决，在列表理解中，如果每个元素的大小小于指定的大小，我们只需要使用字符串格式来执行可选的 0 填充。

```
# Python3 code to demonstrate 
# K length Padding in List
# using list comprehension

# initializing list 
test_list = [3, 54, 4, 100, 10]

# printing original list
print ("The original list is : " + str(test_list))

# initializing K 
K = 4

# using list comprehension
# K length Padding in List
temp = "% 0" + str(K) + "d"
res = [temp % i for i in test_list]

# printing result 
print ("The list after K size element padding : " + str(res))
```

**Output :**

```
The original list is : [3, 54, 4, 100, 10]
The list after K size element padding ['0003', '0054', '0004', '0100', '0010']

```