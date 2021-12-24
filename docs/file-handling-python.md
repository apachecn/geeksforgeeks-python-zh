# Python 中的文件处理

> 原文:[https://www.geeksforgeeks.org/file-handling-python/](https://www.geeksforgeeks.org/file-handling-python/)

Python 也支持文件处理，并允许用户处理文件，即读写文件，以及许多其他文件处理选项，对文件进行操作。文件处理的概念已经扩展到各种其他语言，但是实现要么复杂要么冗长，但是像 Python 的其他概念一样，这里的这个概念也很简单和简短。Python 将文件不同地视为文本或二进制文件，这一点很重要。每行代码包括一系列字符，它们形成文本文件。文件的每一行都以一个特殊字符结束，称为结束字符或行尾字符，如逗号{，}或换行符。它结束当前行，并告诉解释器新的一行已经开始。让我们从读写文件开始。

### **开启()功能的工作**

在对文件执行任何操作(如读或写)之前，我们首先必须打开该文件。为此，我们应该使用 Python 的内置函数 open()

但是在打开的时候，我们要指定模式，代表打开文件的目的。

```
f = open(filename, mode)
```

其中支持以下模式:

1.  **r:** 打开现有文件进行读取操作。
2.  **w:** 打开现有文件进行写操作。如果文件已经包含一些数据，那么它将被覆盖。
3.  **a:** 打开现有文件进行追加操作。它不会覆盖现有数据。
4.  **r+:** 向文件中读写数据。文件中以前的数据不会被删除。
5.  **w+:** 写入和读取数据。它将覆盖现有数据。
6.  **a+:** 从文件中追加和读取数据。它不会覆盖现有数据。

看看下面的例子:

## 蟒蛇 3

```
# a file named "geek", will be opened with the reading mode.
file = open('geek.txt', 'r')
# This will print every line one by one in the file
for each in file:
    print (each)
```

open 命令将以读取模式打开文件，for 循环将打印文件中的每一行。

### **读取()模式工作**

在 Python 中，读取文件的方式不止一种。如果你需要提取一个包含文件中所有字符的字符串，那么我们可以使用 **file.read()** 。完整的代码如下所示:

## 蟒蛇 3

```
# Python code to illustrate read() mode
file = open("file.text", "r")
print (file.read())
```

读取文件的另一种方法是调用一定数量的字符，如下面的代码，解释器将读取存储数据的前五个字符，并将其作为字符串返回:

## 蟒蛇 3

```
# Python code to illustrate read() mode character wise
file = open("file.txt", "r")
print (file.read(5))
```