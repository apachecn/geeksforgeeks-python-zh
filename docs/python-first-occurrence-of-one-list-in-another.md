# Python–一个列表在另一个列表中的首次出现

> 原文:[https://www . geesforgeks . org/python-一个列表中的第一个出现/](https://www.geeksforgeeks.org/python-first-occurrence-of-one-list-in-another/)

给定两个列表，任务是编写一个 Python 程序，从列表 2 中提取列表 1 中出现的第一个元素。

**示例:**

> **输入:** test_list1 = [1，6，3，7，8，9，2]，test_list2 = [4，10，8，2，0，11]
> 
> **输出:** 8
> 
> **说明:** 8 是列表 2 的第一个元素，出现在列表 1 的第五个索引中。
> 
> **输入:** test_list1 = [1，6，3，7，8，9，2]，test_list2 = [4，10，18，12，0，11]
> 
> **输出:**无
> 
> **说明:**在列表 1 中找不到列表 2 的元素。

**进场:使用** [**集合()**](https://www.geeksforgeeks.org/python-set-method/) **+下一个()**

在这种情况下，最初将检查容器转换为 set，并使用 next()和生成器表达式检查每个元素。next()函数返回第一个匹配的元素，否则如果没有找到匹配的元素，则返回 None。

## 蟒蛇 3

```py
# Python3 code to demonstrate working of
# First occurrence of one list in another
# Using next() + set()

# initializing lists
test_list1 = [1, 6, 3, 7, 8, 9, 2]
test_list2 = [4, 10, 8, 2, 0, 11]

# printing original lists
print("The original list 1 is : " + str(test_list1))
print("The original list 2 is : " + str(test_list2))

# converting test list to sets
test_list2 = set(test_list2)

# stops when 1st match element is found
res = next((ele for ele in test_list1 if ele in test_list2), None)

# printing result
print("First element in list 1 from 2 : " + str(res))
```

**输出:**

```py
The original list 1 is : [1, 6, 3, 7, 8, 9, 2]
The original list 2 is : [4, 10, 8, 2, 0, 11]
First element in list 1 from 2 : 8
```