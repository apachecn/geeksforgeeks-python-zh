# Python–交替字符串连接

> 原文:[https://www . geesforgeks . org/python-alternate-strings-concation/](https://www.geeksforgeeks.org/python-alternate-strings-concatenation/)

获得一个列表的连接的问题是非常普遍的，我们可能有一天会面临获得交替元素的连接的问题，并获得包含交替元素的连接的 2 个元素的列表。让我们讨论一下实现这一点的某些方法。

**方法#1:使用列表理解+列表切片+ `join()`**
使用列表理解的列表切片可以用来执行这个特定的任务。我们可以通过列表理解来运行逻辑，列表切片可以通过 join()函数将替换字符分割出来。

```
# Python3 code to demonstrate
# Alternate Strings Concatenation
# using list comprehension + list slicing

# initializing list 
test_list = ["GFG", "is", "for", "Computer", "Science", "learning"]

# printing original list 
print("The original list : " + str(test_list))

# using list comprehension + list slicing
# Alternate Strings Concatenation
res = [" ".join(test_list[i : : 2]) for i in range(len(test_list) //
                                                  (len(test_list)//2))]

# print result
print("The alternate elements concatenation list : " + str(res))
```

**Output :**

```
The original list : ['GFG', 'is', 'for', 'Computer', 'Science', 'learning']
The alternate elements concatenation list : ['GFG for Science', 'is Computer learning']

```