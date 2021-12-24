# Python |提取字符串的分数列表

> 原文:[https://www . geesforgeks . org/python-extract-score-list-of-string/](https://www.geeksforgeeks.org/python-extract-score-list-of-string/)

有时，在编程时，我们会遇到这样一个问题:我们为字母表中的每个字符指定一个特定的分数，然后根据字符串，只提取这些分数用于进一步的计算。这在游戏领域可以有应用。让我们讨论执行这项任务的某些方法。

**方法#1:使用列表理解+ `ord()`**
以上功能的组合可以用来执行这个任务。在本文中，我们使用列表理解来执行元素迭代的任务，而 order()执行检查必须返回的列表索引的任务。

```
# Python3 code to demonstrate working of
# Extract Score list of String
# using list comprehension + ord()

# initialize list and string 
test_list = [3, 4, 5, 7, 5, 8, 1, 5, 7, 10,
             6, 7, 9, 11, 3, 1, 3, 6, 7, 9,
             7, 4, 6, 4, 2, 1]

test_str = "geeksforgeeks"

# printing original list and string
print("The original list : " + str(test_list))
print("The original string : " + str(test_str))

# Extract Score list of String
# using list comprehension + ord()
res = [test_list[ord(ele) - 97] for ele in test_str]

# printing result
print("The Score list is : " + str(res))
```

**Output :**

> 原始列表:【3、4、5、7、5、8、1、5、7、10、6、7、9、11、3、1、3、6、7、9、7、4、6、4、2、1】
> 原始字符串:geeksforgeeks
> 分数列表为:【1、5、5、6、7、8、3、6、1、5、6、7】