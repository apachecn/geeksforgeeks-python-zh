# 如何记录 Python 异常？

> 原文:[https://www . geesforgeks . org/how-log-a-python-exception/](https://www.geeksforgeeks.org/how-to-log-a-python-exception/)

要在 Python 中记录异常，我们可以使用**记录**模块，通过该模块我们可以记录错误。

日志模块提供了一组简单日志记录的功能，用于以下目的

*   调试
*   信息
*   警告
*   错误
*   批评的

在 python 中记录有错误的异常可以通过 **logging.exception()** 方法完成。此函数在此记录器上记录一条错误级别为 ERROR 的消息。参数被解释为用于调试()。异常信息被添加到日志消息中。只能从异常处理程序中调用此方法。

为更清楚起见，请参见以下代码:

**例 1 :**

## 蟒蛇 3

```py
# importing the module
import logging

try:
    printf("GeeksforGeeks")
except Exception as Argument:
    logging.exception("Error occurred while printing GeeksforGeeks")
```

**输出:**

```py
ERROR:root:Error occurred while printing GeeksforGeeks
Traceback (most recent call last):
  File "/home/gfg.py", line 3, in 
    printf("GeeksforGeeks")
NameError: name 'printf' is not defined
```

**示例 2:** 我们还可以通过以下方法将错误消息记录到不同的文件中，而不会在控制台中显示错误:

## 蟒蛇 3

```py
# importing the module
import logging

try:
    printf("GeeksforGeeks")
except Exception as Argument:

     # creating/opening a file
     f = open("demofile2.txt", "a")

     # writing in the file
     f.write(str(Argument))

     # closing the file
     f.close()
```

错误信息将存储在文件名*demofile 2 . txt*中，与代码位于同一目录。

**输出:**

```py
Traceback (most recent call last):
  File "/home/gfg.py", line 5, in 
    printf("GeeksforGeeks")
NameError: name 'printf' is not defined
```