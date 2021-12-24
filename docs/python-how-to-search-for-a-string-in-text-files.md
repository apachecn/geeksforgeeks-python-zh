# Python–如何在文本文件中搜索字符串？

> 原文:[https://www . geesforgeks . org/python-如何在文本文件中搜索字符串/](https://www.geeksforgeeks.org/python-how-to-search-for-a-string-in-text-files/)

在本文中，我们将看到如何在文本文件中搜索特定的字符串。

**考虑以下文本文件:**

![](img/fc4391865b3390da6e09ad78a207dfe2.png)

**示例 1:** 我们将逐行搜索字符串，如果找到字符串，我们将打印该字符串和行号。

**步骤:**

*   打开文件。
*   将变量索引和标志设置为零。
*   逐行遍历文件。
*   在循环检查条件中，使用“In”运算符检查行中是否存在字符串。如果发现标志为 0。
*   循环后，再次检查是否设置了标志条件。如果找到设置字符串，则打印一个字符串和行号，否则只需打印消息“字符串未找到”。
*   关闭文件。

**代码:**

## 蟒蛇 3

```
string1 = 'coding'

# opening a text file
file1 = open("geeks.txt", "r")

# setting flag and index to 0
flag = 0
index = 0

# Loop through the file line by line
for line in file1:  
    index + = 1 

    # checking string is present in line or not
    if string1 in line:

      flag = 1
      break 

# checking condition for string found or not
if flag == 0: 
   print('String', string1 , 'Not Found') 
else: 
   print('String', string1, 'Found In Line', index)

# closing text file    
file1.close() 
```

**输出:**

![](img/d9c24d294cd2a22a15c1f2d278a01d04.png)

**示例 2:** 我们只是在查找文件中是否存在字符串。

**步骤:**

*   打开一个文件。
*   读取文件并将其存储在变量中。
*   使用“in”运算符检查文件中是否存在字符串。
*   如果条件为真，则打印消息“找到字符串”，否则打印“找不到字符串”。
*   关闭文件。

#### 代码:

## 蟒蛇 3

```
string1 = 'portal'

# opening a text file
file1 = open("geeks.txt", "r")

# read file content
readfile = file1.read()

# checking condition for string found or not
if string1 in readfile: 
    print('String', string1, 'Found In File')
else: 
    print('String', string1 , 'Not Found') 

# closing a file
file1.close() 
```

**输出:**

![](img/d0980f4f676fc58db3fd35d9a90f8091.png)