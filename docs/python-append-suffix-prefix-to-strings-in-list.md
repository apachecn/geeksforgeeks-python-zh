# Python |在列表

的字符串中添加后缀/前缀

> 原文:[https://www . geesforgeks . org/python-append-后缀-前缀-列表中的字符串/](https://www.geeksforgeeks.org/python-append-suffix-prefix-to-strings-in-list/)

有时，在使用 Python 时，我们会遇到一个问题，即我们需要在列表的末尾或前面填充字符串。这种问题很常见，可能发生在日常编程或 web 开发中。让我们讨论一下执行这项任务的方法。

**方法:使用`+ operator` +列表理解**

在这个任务中，我们只需使用+运算符在后面或前面添加字符串，并使用列表理解来遍历所有元素。

```
# Python3 code to demonstrate working of
# Append suffix / prefix to strings in list
# Using list comprehension + "+" operator

# initializing list
test_list = ['a', 'b', 'c', 'd']

# printing list
print("The original list : " + str(test_list))

# initializing append_str
append_str = 'gfg'

# Append suffix / prefix to strings in list
pre_res = [append_str + sub for sub in test_list]
suf_res = [sub + append_str for sub in test_list]

# Printing result
print("list after prefix addition : " + str(pre_res))
print("list after suffix addition : " + str(suf_res))
```

**输出:**

```

The original list : ['a', 'b', 'c', 'd']
list after prefix addition : ['gfga', 'gfgb', 'gfgc', 'gfgd']
list after suffix addition : ['agfg', 'bgfg', 'cgfg', 'dgfg']

```