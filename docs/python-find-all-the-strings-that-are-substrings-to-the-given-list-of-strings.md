# Python–找到给定字符串列表的所有子字符串

> 原文:[https://www . geeksforgeeks . org/python-查找所有字符串-字符串列表的子字符串/](https://www.geeksforgeeks.org/python-find-all-the-strings-that-are-substrings-to-the-given-list-of-strings/)

给定两个列表，任务是编写一个 Python 程序来提取所有字符串，这些字符串可能是另一个列表中任何字符串的子串。

**示例:**

> **输入:**test _ list 1 =[“Geeks forgeeks”、“best”、“for”、“Geeks”]，test _ list 2 =[“Geeks”、“win”、“or”、“learn”]
> 
> **输出:** ['极客'，'或']
> 
> **解释:**“Geeks”作为子串出现在“Geeksforgeeks”字符串中。
> 
> **输入:**test _ list 1 =[“Geeks forgeeks”、“best”、“4”、“Geeks”]，test _ list 2 =[“Geeks”、“win”、“or”、“learn”]
> 
> **输出:** []
> 
> **说明:**未发现子串。

**方法一:使用列表理解**

在本文中，我们使用嵌套循环执行任务，并使用列表理解进行测试，如果字符串是其他列表的任何子字符串的一部分，则提取该字符串。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Substring Intersections
# Using list comprehension

# initializing lists
test_list1 = ["Geeksforgeeks", "best", "for", "geeks"]
test_list2 = ["Geeks", "win", "or", "learn"]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# using list comprehension for nested loops
res = list(
    set([ele1 for sub1 in test_list1 for ele1 in test_list2 if ele1 in sub1]))

# printing result
print("Substrings Intersections : " + str(res))
```

**输出:**

> 最初的名单 1 是:[‘极客’，‘最佳’，‘适合’，‘极客’
> 
> 最初的名单 2 是:['极客'，'赢'，'或'，'学习']
> 
> 子字符串交集:['或'，'极客']

**方法 2:使用任意()+生成器表达式**

在这种情况下，any()用于检查要匹配的字符串列表中任何字符串的子字符串匹配情况。

## 蟒蛇 3

```
# Python3 code to demonstrate working of
# Substring Intersections
# Using any() + generator expression

# initializing lists
test_list1 = ["Geeksforgeeks", "best", "for", "geeks"]
test_list2 = ["Geeks", "win", "or", "learn"]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# any() returns the string after match in any string
# as Substring
res = [ele2 for ele2 in test_list2 if any(ele2 in ele1 for ele1 in test_list1)]

# printing result
print("Substrings Intersections : " + str(res))
```

**输出:**

> 最初的名单 1 是:[‘极客’，‘最佳’，‘适合’，‘极客’
> 
> 最初的名单 2 是:['极客'，'赢'，'或'，'学习']
> 
> 子字符串交集:['极客'，'或'