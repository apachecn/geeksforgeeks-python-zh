# 如何在 Python 中读取文件

> 原文:[https://www . geesforgeks . org/如何从 python 文件中读取/](https://www.geeksforgeeks.org/how-to-read-from-a-file-in-python/)

Python 提供了创建、写入和读取文件的内置功能。python 中可以处理两种类型的文件，普通文本文件和二进制文件(用二进制语言编写，0 和 1)。

*   **Text file:** In this type of file, each line of text ends with a special character named EOL (end of line), which is a new line character ('\n') in python by default.
*   **Binary file:** In this type of file, there is no terminator in one line, and the data is stored after being converted into a binary language that can be understood by the machine.

**注意:**想了解更多文件处理[点击这里](https://www.geeksforgeeks.org/reading-writing-text-files-python/)。

#### 存取方式

访问模式控制打开的文件中可能的操作类型。它指的是文件打开后将如何使用。这些模式还定义了文件句柄在文件中的位置。文件句柄就像一个光标，它定义了从哪里读取或写入文件中的数据。读取文件的不同访问模式有–

1.  **只读(' r') :** 打开文本文件阅读。句柄位于文件的开头。如果文件不存在，将引发输入/输出错误。这也是打开文件的默认模式。
2.  **读写(' r+') :** 打开文件进行读写。句柄位于文件的开头。如果文件不存在，将引发输入/输出错误。
3.  **追加并读取(' a+') :** 打开文件进行读写。如果文件不存在，则创建该文件。句柄位于文件的末尾。正在写入的数据将被插入到现有数据的末尾。

**注意:**想了解更多访问模式[点击这里](https://www.geeksforgeeks.org/reading-writing-text-files-python/)。

## 打开文件

使用 `open()`功能完成。此功能不需要导入任何模块。

**语法:**

```
File_object = open(r"File_Name", "Access_Mode")

```

该文件应该与 python 程序文件存在于同一个目录中，否则文件的完整地址应该写在文件名的位置。

**注意:**将`r`放在文件名之前，以防止文件名字符串中的字符被视为特殊字符。例如，如果文件地址中有\u temp，则\u t 将被视为 tab 字符，并在无效地址中引发错误。r 使字符串原始，也就是说，它告诉字符串没有任何特殊字符。如果文件在同一个目录中并且地址没有被放置，r 可以被忽略。

```
# Open function to open the file "MyFile1.txt"  
# (same directory) in read mode and 
file1 = open("MyFile.txt", "r") 

# store its reference in the variable file1  
# and "MyFile2.txt" in D:\Text in file2 
file2 = open(r"D:\Text\MyFile2.txt", "r+") 
```

这里，文件 1 被创建为我的文件 1 的对象，文件 2 被创建为我的文件 2 的对象。

## 关闭文件

`close()`函数关闭文件并释放该文件获取的内存空间。当不再需要该文件时，或者如果要以不同的文件模式打开该文件时，将使用它。

**语法:**

```
File_object.close()

```

```
# Opening and Closing a file "MyFile.txt" 
# for object name file1. 
file1 = open("MyFile.txt", "r") 
file1.close() 
```

## 从文件中读取

从文本文件中读取数据有三种方法。

*   **Read ():** Returns the read byte as a string. Read n bytes, if n is not specified, read the whole file.

    ```
    File_object.read([n])

    ```

*   **Readline ():** Read a line of the file and return it as a string. For the specified n, read up to n bytes. However, multiple lines will not be read, even if n exceeds the length of the line.

    ```
    File_object.readline([n])

    ```

*   **Readline ():** Read all rows and return them as string elements of each row in the list.

    ```
    File_object.readlines()

    ```

**注意:** `‘\n’`被视为两个字节的特殊字符。

**例:**

```
# Program to show various ways to 
# read data from a file. 

# Creating a file
file1 = open("myfile.txt", "w")
L = ["This is Delhi \n", "This is Paris \n", "This is London \n"]

# Writing data to a file
file1.write("Hello \n") 
file1.writelines(L)
file1.close()  # to change file access modes

file1 = open("myfile.txt", "r+")

print("Output of Read function is ")
print(file1.read())
print()

# seek(n) takes the file handle to the nth
# bite from the beginning. 
file1.seek(0)

print("Output of Readline function is ")
print(file1.readline())
print()

file1.seek(0)

# To show difference between read and readline 
print("Output of Read(9) function is ")
print(file1.read(9))
print()

file1.seek(0)

print("Output of Readline(9) function is ")
print(file1.readline(9))
print()

file1.seek(0)

# readlines function 
print("Output of Readlines function is ")
print(file1.readlines())
print()
file1.close() 
```

**输出:**

```
Output of Read function is
Hello
This is Delhi
This is Paris
This is London

Output of Readline function is
Hello

Output of Read(9) function is
Hello
Th

Output of Readline(9) function is
Hello

Output of Readlines function is
['Hello \n', 'This is Delhi \n', 'This is Paris \n', 'This is London \n']

```

#### 带语句

`with` Python 中的语句用于异常处理，使代码更加清晰，可读性更强。它简化了文件流等公共资源的管理。与上述实现不同，使用 with 语句时不需要调用`file.close()`。`with`声明本身确保了资源的适当获取和释放。

**语法:**

```
with open filename as file:

```

```
# Program to show various ways to
# read data from a file.

L = ["This is Delhi \n", "This is Paris \n", "This is London \n"]

# Creating a file
with open("myfile.txt", "w") as file1:
    # Writing data to a file
    file1.write("Hello \n")
    file1.writelines(L)
    file1.close()  # to change file access modes

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

```

**注:**欲了解更多关于[的声明，请点击此处](https://www.geeksforgeeks.org/with-statement-in-python/)。