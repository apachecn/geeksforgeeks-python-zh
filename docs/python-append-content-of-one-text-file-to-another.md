# Python–将一个文本文件的内容附加到另一个文本文件中

> 原文:[https://www . geesforgeks . org/python-将一个文本文件的内容追加到另一个文本文件中/](https://www.geeksforgeeks.org/python-append-content-of-one-text-file-to-another/)

用户输入两个文件名后，任务是将第二个文件的内容附加到第一个文件的内容上。
**例**

```py
Input :
file1.txt
file2.txt

Output :
Content of first file (before appending) - geeksfor
Content of second file (before appending) - geeks
Content of first file (after appending) - geeksforgeeks
Content of second file (after appending) - geeks
```

**算法:**

1.  输入文件的名称。
2.  使用 Open()函数以只读模式打开这两个文件。
3.  在使用 read()函数追加之前，打印文件的内容。
4.  使用 Close()函数关闭这两个文件。
5.  以追加模式打开第一个文件，以读取模式打开第二个文件。
6.  使用 write()函数将第二个文件的内容追加到第一个文件中。
7.  使用 seek()函数将文件的光标重新定位在开头。
8.  打印附加文件的内容。
9.  关闭两个文件。

假设文本文件 file1.txt 和 file2.txt 包含以下数据。
**文件**

![file1.txt](img/b75822e3bb080c22446f208671947bb8.png)

**file2.txt**

![](img/8e860f6776c37d46f21aaaa0dce92ab2.png)

## 蟒蛇 3

```py
# entering the file names
firstfile = input("Enter the name of first file ")
secondfile = input("Enter the name of second file ")

# opening both files in read only mode to read initial contents
f1 = open(firstfile, 'r')
f2 = open(secondfile, 'r')

# printing the contens of the file before appending
print('content of first file before appending -', f1.read())
print('content of second file before appending -', f2.read())

# closing the files
f1.close()
f2.close()

# opening first file in append mode and second file in read mode
f1 = open(firstfile, 'a+')
f2 = open(secondfile, 'r')

# appending the contents of the second file to the first file
f1.write(f2.read())

# relocating the cursor of the files at the beginning
f1.seek(0)
f2.seek(0)

# printing the contents of the files after appendng
print('content of first file after appending -', f1.read())
print('content of second file after appending -', f2.read())

# closing the files
f1.close()
f2.close()
```

**输出:**

![Python - Append content of one text file to another](img/9441c9211adae6e22b1d71406d6b2aa4.png)