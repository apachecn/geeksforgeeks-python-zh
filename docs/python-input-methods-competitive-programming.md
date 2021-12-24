# 竞技编程的 Python 输入法

> 原文:[https://www . geesforgeks . org/python-输入-方法-竞争-编程/](https://www.geeksforgeeks.org/python-input-methods-competitive-programming/)

Python 是一种非常用户友好的语言，唯一的缺点是速度慢。与 C、C++和 Java 相比，它相当慢。在线编码平台，如果提供的 C/C++限制是 **X** 。通常在 Java 时间提供的是 **2X** 和 Python，是 **5X** 。
为了提高输入输出密集型问题的代码执行速度，语言有各种各样的输入输出过程。

**一个示例问题:**
考虑一个寻找从用户输入的 **N** 个数字之和的问题。
输入一个数字 **N** 。
输入 **N** 个数字用一行中的一个空格隔开。

**示例:**

```
Input : 
5
1 2 3 4 5
Output :
15
```

**上述问题的不同 Python 解决方案:**

**正常方法 Python: (Python 2.7)**
1。 **raw_input()** 接受可选的提示参数。它还会从返回的字符串中去除尾随的换行符。
2。 **print** 只是一个薄薄的包装器，它格式化输入(末尾的 args 和 newline 之间的空间)并调用给定对象的 write 函数。

## 计算机编程语言

```
# basic method of input output
# input N
n = int(raw_input())

# input the array
arr = [int(x) for x in raw_input().split()]

# initialize variable
summation = 0

# calculate sum
for x in arr:
    summation += x

# print answer
print(summation)
```

**使用内置 stdin、stdout 的速度稍快的方法:(Python 2.7)**
1。**系统标准**另一方面是**文件对象**。这就像创建任何其他可以从文件中读取输入的文件对象一样。在这种情况下，文件将是一个标准的输入缓冲区。
2。 **stdout.write('D\n')** 比**打印' D'** 快。
3。更快的是通过 **stdout.write(")一次写完。连接(列表-理解))**但是这使得内存使用依赖于输入的大小。

## 计算机编程语言

```
# import inbuilt standard input output
from sys import stdin, stdout

# suppose a function called main() and
# all the operations are performed
def main():

    # input via readline method
    n = stdin.readline()

    # array input similar method
    arr = [int(x) for x in stdin.readline().split()]

    #initialize variable
    summation = 0

    # calculate sum
    for x in arr:
        summation += x

    # could use inbuilt summation = sum(arr)

    # print answer via write
    # write method writes only
    # string operations
    # so we need to convert any
    # data into string for input
    stdout.write(str(summation))

# call the main method
if __name__ == "__main__":
    main()   
```

**时差:**

> 定时汇总(每条 100k 行)
> ————————
> 打印:6.040 秒
> 写入文件:0.122 秒
> 带标准输出打印:0.121 秒

正如我们到目前为止所看到的，从标准系统中获取输入并向标准系统提供输出对于提高代码的效率总是一个好主意，这在竞争性编程中总是需要的。但是等等！你愿意每次需要的时候都写这些长行吗？那么，使用 Python 有什么好处。
我们来讨论一下这个问题的解决方案。我们可以做的是，让我们创建单独的函数来获取各种类型的输入，并在需要的时候调用它们。

### 当您想要输入单行给出的特定整数时

假设输入为以下形式

```
5 7 19 20
```

我们需要单独的变量来引用它们。我们想要的是:

```
a = 5
b = 7
c = 19
d = 20
```

因此，我们可以创建一个名为 **get_ints()** 的函数，如下所示:

## 蟒蛇 3

```
import sys
def get_ints(): return map(int, sys.stdin.readline().strip().split())

a,b,c,d = get_ints()
```

现在你不用反复写这一行了。你只需要调用 **get_ints()** 函数就可以接受这种形式的输入。在功能*中，我们使用的是 [*地图*](https://www.geeksforgeeks.org/python-map-function/) 功能。*

### 当您想要输入单行给出的整数列表时

假设输入为以下形式

```
1 2 3 4 5 6 7 8
```

我们希望一个变量可以保存整数的完整列表。我们想要的是:

```
Arr = [1, 2, 3, 4, 5, 6, 7, 8]
```

因此，这里我们将创建一个名为 **get_list()** 的函数，如下所示:

## 蟒蛇 3

```
import sys
def get_ints(): return list(map(int, sys.stdin.readline().strip().split()))

Arr = get_ints()
```

现在你不用反复写这一行了。你只需要调用 **get_ints()** 函数，就可以以这种形式输入

### 当您想要输入字符串时

假设输入为以下形式

```
GeeksforGeeks is the best platform to practice Coding.
```

我们希望有一个引用变量来保存这个字符串。我们想要的是:

```
string = "GeeksforGeeks if the best platform to practice coding."
```

因此，这里我们将创建一个名为 **get_string()** 的函数，如下所示:

## 蟒蛇 3

```
import sys
def get_string(): return sys.stdin.readline().strip()

string = get_string()
```

现在你不用反复写这一行了。你只需要调用 **get_string()** 函数就可以以这种形式输入
**添加一个缓冲管道 io: (Python 2.7)**
1。简单来说，在提交代码之前添加缓冲的 IO 代码，让输出更快。
2。 **io 的好处。BytesIO** 对象是它们实现了一个公共接口(通常被称为“类似文件”的对象)。 **BytesIO** 对象有一个内部指针，每次调用 read(n)指针都会前进。
3。 **atexit** 模块提供了一个简单的界面，用于注册程序正常关闭时要调用的功能。 **sys** 模块也提供了一个钩子，sys.exitfunc，但是那里只能注册一个功能。**退出注册表**可以被多个模块和库同时使用。

## 计算机编程语言

```
# template begins
#####################################

# import libraries for input/ output handling
# on generic level
import atexit, io, sys

# A stream implementation using an in-memory bytes
# buffer. It inherits BufferedIOBase.
buffer = io.BytesIO()
sys.stdout = buffer

# print via here
@atexit.register
def write():
    sys.__stdout__.write(buffer.getvalue())

#####################################
# template ends

# normal method followed
# input N
n = int(raw_input())

# input the array
arr = [int(x) for x in raw_input().split()]

# initialize variable
summation = 0

# calculate sum
for x in arr:
    summation += x

# print answer
print(summation)
```

通常在处理大量数据时，正常方法无法在时限内执行。方法 2 有助于维护大量的输入/输出数据。方法 3 是最快的。通常，方法 2 和方法 3 有助于处理大于 2 或 3 MBs 的输入数据文件。
**注意:**上面提到的代码都在 Python 2.7 中，要在 Python 3 中使用。x 版本。只需将 **raw_input()** 替换为 Python 3。x 的[输入()](https://docs.python.org/3.5/library/functions.html?highlight=input#input)语法。休息应该没问题。
**参考文献:**
1。[Python 2.7 中关于输入的更多信息](https://docs.python.org/2/library/functions.html?highlight=raw_input#raw_input)
2。[通过 sys 库和其他命令输出。](https://docs.python.org/2/library/sys.html?highlight=stdout#sys.stdout)
3。[通过系统库和其他命令输入。](https://docs.python.org/2/library/sys.html?highlight=stdin#sys.stdin)
4。 [Python 退出模块文档。](https://docs.python.org/3/library/atexit.html)
本文由 **Shubham Saxena** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以用[write.geeksforgeeks.org](https://write.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。
如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。