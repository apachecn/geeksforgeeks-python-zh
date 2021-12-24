# Python |根据给定的字符串列表过滤列表

> 原文:[https://www . geesforgeks . org/python-filter-a-list-based-on-to-list-of-strings/](https://www.geeksforgeeks.org/python-filter-a-list-based-on-the-given-list-of-strings/)

给定一个列表，任务是根据另一个字符串列表从列表中过滤元素。这些类型的问题在抓取网站时很常见。

**示例:**

```py
Input:
List_string1 = ['key', 'keys', 'keyword', 'keychain', 'keynote']
List_string2 = ['home/key/1.pdf',
         'home/keys/2.pdf', 
         'home/keyword/3.pdf', 
         'home/keychain/4.pdf',
         'home/Desktop/5.pdf', 
         'home/keynote/6.pdf']
Output:
['home/Desktop/5.pdf']

Explanation: We filter only those element from 
list_string2 that do not have string in list_string1

```

以下是实现上述任务的一些方法。

**方法#1:使用迭代**

```py
# Python code to  filter element from list 
# based on another list of string.

# List Initialization
Input = ['key', 'keys', 'keyword', 'keychain', 'keynote']
Input_string = ['home/key/1.pdf',
         'home/keys/2.pdf', 
         'home/keyword/3.pdf', 
         'home/keychain/4.pdf',
         'home/Desktop/5.pdf', 
         'home/keynote/6.pdf']

Output = Input_string.copy()
temp = []

# Using iteration
for elem in Input_string:
    for n in Input:
        if n in elem:
            temp.append(elem)

for elem in temp:
    if elem in Output:
        Output.remove(elem)

# Printing
print("List of keywords are:", Input)
print("Given list:", Input_string)
print("filtered list is :", Output)
```

**Output:**

> 关键词列表为:['key '，' keys '，' keynote '，' keynote']
> 给定列表:['home/key/1.pdf '，' home/keynote/2 . pdf '，' home/keynote/3 . pdf '，' home/keynote/4 . pdf '，' home/Desktop/5.pdf '，' home/keynote/6.pdf']
> 过滤列表为:['home/Desktop/5.pdf']

**方法二:使用列表理解**

```py
# Python code to  filter element from list 
# based on another list of string.

# List Initialization
Input = ['key', 'keys', 'keyword', 'keychain', 'keynote']
Input_string = ['home/key/1.pdf',
         'home/keys/2.pdf', 
         'home/keyword/3.pdf', 
         'home/keychain/4.pdf',
         'home/Desktop/5.pdf', 
         'home/keynote/6.pdf']

# Using list comprehension
Output = [b for b in Input_string if
          all(a not in b for a in Input)]

# Printing
print("List of keywords are:", Input)
print("Given list:", Input_string)
print("filtered list is :", Output)
```

**Output:**

> 关键词列表为:['key '，' keys '，' keynote '，' keynote']
> 给定列表:['home/key/1.pdf '，' home/keynote/2 . pdf '，' home/keynote/3 . pdf '，' home/keynote/4 . pdf '，' home/Desktop/5.pdf '，' home/keynote/6.pdf']
> 过滤列表为:['home/Desktop/5.pdf']