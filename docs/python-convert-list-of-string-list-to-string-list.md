# Python |将字符串列表转换为字符串列表

> 原文:[https://www . geesforgeks . org/python-convert-list-of-string-list-to-string-list/](https://www.geeksforgeeks.org/python-convert-list-of-string-list-to-string-list/)

有时在 Python 中工作时，我们会遇到数据相互转换的问题。本文讨论列表字符串列表到连接字符串列表的转换。让我们讨论执行这项任务的某些方法。

**方法#1:使用`map() + generator expression + join() + isdigit()`**
该任务可以使用上述功能的组合来执行。在本文中，我们使用连接来连接数字，并构造一个字符串整数。map()用于将逻辑应用于列表中的每个元素。

```
# Python3 code to demonstrate working of
# Convert List of String List to String List
# using map() + generator expression + join() + isdigit()

# helper function 
def convert(sub):
    return "".join(ele if ele.isdigit() else "" for ele in sub)

# initialize list 
test_list = ["[1, 4]", "[5, 6]", "[7, 10]"]

# printing original list 
print("The original list : " + str(test_list))

# Convert List of String List to String List
# using map() + generator expression + join() + isdigit()
res = list(map(convert, test_list))

# printing result
print("List after performing conversion : " + str(res))
```

**Output :**

```
The original list : ['[1, 4]', '[5, 6]', '[7, 10]']
List after performing conversion : ['14', '56', '710']

```