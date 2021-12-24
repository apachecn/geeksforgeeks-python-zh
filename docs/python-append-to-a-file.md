# Python 追加到文件中

> 原文:[https://www.geeksforgeeks.org/python-append-to-a-file/](https://www.geeksforgeeks.org/python-append-to-a-file/)

**先决条件:**

*   [Basic knowledge of document processing](https://www.geeksforgeeks.org/reading-writing-text-files-python/)
*   [Access mode](https://www.geeksforgeeks.org/reading-writing-text-files-python/)

在读取或写入文件时，访问模式控制打开的文件中可能的操作类型。它指的是文件打开后将如何使用。这些模式还定义了文件句柄在文件中的位置。文件句柄就像一个光标，它定义了从哪里读取或写入文件中的数据。

为了在现有文件中添加新行，使用`'a'`或`'a+'`作为访问模式，在附加模式下打开文件。这些访问模式的定义如下:

*   **仅追加(' a'):** 打开文件进行写入。如果文件不存在，则创建该文件。句柄位于文件的末尾。正在写入的数据将被插入到现有数据的末尾。
*   **追加并读取(' a+'):** 打开文件进行读写。如果文件不存在，则创建该文件。句柄位于文件的末尾。正在写入的数据将被插入到现有数据的末尾。

当文件以追加模式打开时，句柄位于文件的末尾。正在写入的数据将被插入到现有数据的末尾。让我们看下面的例子来阐明写模式和追加模式之间的区别。

**例:**

```
# Python program to illustrate
# Append vs write mode
file1 = open("myfile.txt", "w")
L = ["This is Delhi \n", "This is Paris \n", "This is London"]
file1.writelines(L)
file1.close()

# Append-adds at last
file1 = open("myfile.txt", "a")  # append mode
file1.write("Today \n")
file1.close()

file1 = open("myfile.txt", "r")
print("Output of Readlines after appending")
print(file1.read())
print()
file1.close()

# Write-Overwrites
file1 = open("myfile.txt", "w")  # write mode
file1.write("Tomorrow \n")
file1.close()

file1 = open("myfile.txt", "r")
print("Output of Readlines after writing")
print(file1.read())
print()
file1.close()
```

**输出:**

```
Output of Readlines after appending
This is Delhi
This is Paris
This is LondonToday

Output of Readlines after writing
Tomorrow

```

#### 从新行追加数据

在上面的例子中，可以看到数据不是从新行追加的。这可以通过在文件中写入换行符`'\n'`来实现。

**注意:** `‘\n’`被视为两个字节的特殊字符。

**例:**

```
# Python program to illustrate
# append from new line

file1 = open("myfile.txt", "w")
L = ["This is Delhi \n", "This is Paris \n", "This is London"]
file1.writelines(L)
file1.close()

# Append-adds at last
# append mode
file1 = open("myfile.txt", "a")  

# writing newline character
file1.write("\n")
file1.write("Today")

# without newline character
file1.write("Tomorrow")

file1 = open("myfile.txt", "r")
print("Output of Readlines after appending")
print(file1.read())
print()
file1.close()
```

**输出:**

```
Output of Readlines after appending
This is Delhi
This is Paris
This is London
TodayTomorrow

```

#### 带语句

`with` Python 中的语句用于异常处理，使代码更加清晰，可读性更强。它简化了文件流等公共资源的管理。与上述实现不同，使用`with` 语句时不需要调用`file.close()`。`with`声明本身确保了资源的正确获取和释放。

**例:**

```
# Program to show various ways to
# append data to a file using
# with statement

L = ["This is Delhi \n", "This is Paris \n", "This is London \n"]

# Writing to file
with open("myfile.txt", "w") as file1:
    # Writing data to a file
    file1.write("Hello \n")
    file1.writelines(L)

# Appending to file
with open("myfile.txt", 'a') as file1:
    file1.write("Today")

# Reading from file
with open("myfile.txt", "r+") as file1:
    # Reading form a file
    print(file1.read())
```

**输出:**

```
Hello
This is Delhi
This is Paris
This is London
Today

```

**注:**欲了解更多关于[的声明，请点击此处](https://www.geeksforgeeks.org/with-statement-in-python/)。