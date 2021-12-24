# 从文本文件中提取数字，并使用 Python 添加它们

> 原文:[https://www . geesforgeks . org/extract-numbers-from-a-text-file-and-add-then-use-python/](https://www.geeksforgeeks.org/extract-numbers-from-a-text-file-and-add-them-using-python/)

Python 也支持文件处理，并允许用户处理文件，即读写文件，以及许多其他文件处理选项，对文件进行操作。Python 中的数据文件处理是在两种类型的文件中完成的:

*   文本文件(。txt 扩展)

*   二进制文件(。仓位扩展)

我们在这里操作。Python 中的. txt 文件。通过这个程序，我们可以从文本文件中的内容中提取数字，并将它们全部相加并打印结果。

#### 方法

阅读文件的内容，我们将匹配字符的类型与 int。如果相等的结果为真，则该数将被添加到分配给变量“a”的内存中存储的数中。我们在这里用值 0 初始化变量“a”。

## 蟒蛇 3

```py
# Python program for writing
# to file

file = open('GFG.txt', 'w')

# Data to be written
data ='Geeks1 f2or G8e8e3k2s0'

# Writing to file
file.write(data)

# Closing file
file.close()
```

使用上面的代码，我们在**写**模式下打开了一个名为‘GFG’的新文件。使用 write()函数，我们在内存中插入了分配给变量数据的数据。之后，我们关闭了文件。
从上面创建的文件中读取并提取整数。

## 蟒蛇 3

```py
# Python program for reading
# from file

h = open('GFG.txt', 'r')

# Reading from the file
content = h.readlines()

# Variable for storing the sum
a = 0

# Iterating through the content
# Of the file
for line in content:

    for i in line:

        # Checking for the digit in
        # the string
        if i.isdigit() == True:

            a += int(i)

print("The sum is:", a)
```

**输出:**

```py
The sum is: 24
```

上述程序强调从名为“GFG”的文本文件中提取数字。此外，这些数字在类型转换后被相加并存储在变量“a”中。