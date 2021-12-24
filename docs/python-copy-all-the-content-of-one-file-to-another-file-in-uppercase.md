# Python–将一个文件的所有内容以大写形式复制到另一个文件中

> 原文:[https://www . geesforgeks . org/python-将一个文件的所有内容以大写形式复制到另一个文件中/](https://www.geeksforgeeks.org/python-copy-all-the-content-of-one-file-to-another-file-in-uppercase/)

在本文中，我们将编写一个 Python 程序，以大写形式将一个文件的所有内容复制到另一个文件中。为了解决这个问题，我们来看看将要用到的一些重要函数的定义:

*   [**open ()**](https://www.geeksforgeeks.org/open-a-file-in-python/) **–** It is used to open files in various modes such as reading, writing, appending, reading and writing.
*   [**write ()**](https://www.geeksforgeeks.org/writing-to-file-in-python/) **–** is used to write the specified text into the file.
*   [**Upper ()**](https://www.geeksforgeeks.org/python-string-upper/) **–** Used to convert all lowercase letters of a string into uppercase letters, and finally return.

## **方法 1:** 使用文件处理进行读写

在这种方法中，我们将在第一个文件中使用**“r”模式**(读取文件)，在第二个文件中使用**“w”模式**(写入文件)。最后，我们将使用 write 方法将第一个文件的内容写入第二个文件。我们将使用上面的方法将内容大写，同时将内容写入第二个文件。

## 蟒蛇

```
# To open the first file in read mode
f1 = open("sample file 1.txt", "r")

# To open the second file in write mode
f2 = open("sample file 2.txt", "w")

# For loop to traverse through the file
for line in f1:

    # Writing the content of the first
    # file to the second file

    # Using upper() function to
    # capitalize the letters
    f2.write(line.upper())  
```