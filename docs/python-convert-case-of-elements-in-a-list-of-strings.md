# Python |转换字符串列表中元素的大小写

> 原文:[https://www . geeksforgeeks . org/python-convert-字符串列表中元素的大小写/](https://www.geeksforgeeks.org/python-convert-case-of-elements-in-a-list-of-strings/)

给定一个字符串列表，编写一个 Python 程序将所有字符串从小写/大写转换为大写/小写。

```py
Input : ['GeEk', 'FOR', 'gEEKS']
Output: ['geeks', 'for', 'geeks']

Input : ['fun', 'Foo', 'BaR']
Output: ['FUN', 'FOO', 'BAR']
```

**方法#1 :** 使用`map` 功能将大写转换为小写

```py
# Python code to convert all string
# from uppercase to lowercase.

# Using map function
out = map(lambda x:x.lower(), ['GeEk', 'FOR', 'gEEKS'])

# Converting it into list
output = list(out)

# printing output
print(output)
```

**Output:**

```py
['geek', 'for', 'geeks']

```

**方法 2:** 使用列表理解将小写转换为大写

```py
# Python code to convert all string
# from uppercase to lowercase.

# Initialisation
input = ['fun', 'Foo', 'BaR']

# Converting
lst = [x.upper() for x in input]

# printing output
print(lst)
```

**Output:**

```py
['FUN', 'FOO', 'BAR']

```