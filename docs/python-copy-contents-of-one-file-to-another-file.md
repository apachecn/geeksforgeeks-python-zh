# Python–将一个文件的内容复制到另一个文件中

> 原文:[https://www . geesforgeks . org/python-将一个文件的内容复制到另一个文件/](https://www.geeksforgeeks.org/python-copy-contents-of-one-file-to-another-file/)

给定两个文本文件，任务是编写一个 Python 程序，将第一个文件的内容复制到第二个文件中。

将要使用的文本文件为 *second.txt* 和 *first.txt* :

![](img/435f4a2f8a7071dc0b8149a574dce20f.png)

**方法#1:** 使用[文件处理](https://www.geeksforgeeks.org/file-handling-python/)进行读取和追加

我们先在*【r】*模式下打开*first . txt*读取*的内容，然后在【a】模式下打开 *second.txt* ，将 *first.txt* 的内容追加到 *second.txt* 中。*

**示例:**

## 蟒蛇 3

```
# open both files
with open('first.txt','r') as firstfile, open('second.txt','a') as secondfile:

    # read content from first file
    for line in firstfile:

             # append content to second file
             secondfile.write(line)
```

**输出:**

![](img/dc15cbef0de08817a17ac7525484f4ff.png)

**方法 2:** 使用[文件处理](https://www.geeksforgeeks.org/file-handling-python/)进行读写

我们先在*【r】*模式下打开*first . txt*读取*的内容，然后在【w】模式下打开 *second.txt* ，将 *first.txt* 的内容写入 *second.txt* 。*

**示例:**

## 蟒蛇 3

```
# open both files
with open('first.txt','r') as firstfile, open('second.txt','w') as secondfile:

    # read content from first file
    for line in firstfile:

             # write content to second file
             secondfile.write(line)
```

**输出:**

![](img/dc15cbef0de08817a17ac7525484f4ff.png)

**方法#3:** 使用 [*shutil.copy()*](https://www.geeksforgeeks.org/python-shutil-copy-method/) 模块

Python 中的 *shutil.copy()* 方法用于将源文件的内容复制到目标文件或目录中。

**例:**

## 蟒蛇 3

```
# import module
import shutil

# use copyfile()
shutil.copyfile('first.txt','second.txt')
```

**输出:**

![](img/dc15cbef0de08817a17ac7525484f4ff.png)