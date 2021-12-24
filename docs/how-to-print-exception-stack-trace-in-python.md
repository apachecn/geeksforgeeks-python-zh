# 如何在 Python 中打印异常堆栈跟踪？

> 原文:[https://www . geesforgeks . org/how-print-exception-stack-trace-in-python/](https://www.geeksforgeeks.org/how-to-print-exception-stack-trace-in-python/)

**先决条件:** [蟒蛇追溯](https://www.geeksforgeeks.org/python-traceback/)

要打印异常的堆栈跟踪，可疑代码将保存在 try 块中，而 except 块将用于处理生成的异常。这里我们将打印堆栈跟踪来处理生成的异常。异常的打印堆栈跟踪有助于理解错误和代码的错误。不仅如此，堆栈跟踪还显示了错误发生的位置。

异常的堆栈跟踪的一般结构:

> *   Trace the recent call.
> *   Location of the program.
> *   The line that encountered an error in the program.
> *   Error name: abnormal related information .

**示例:**

```py
Traceback (most recent call last):
  File "C:/Python27/hdg.py", line 5, in 
    value=A[5]
IndexError: list index out of range

```

**方法 1:** 使用 **print_exc()** 方法。

此方法 p 将异常信息和堆栈跟踪条目从追溯对象 *tb* 打印到*文件。*

> **语法:**回溯. print_exc( *限制=无*，*文件=无*，*链=真* )
> 
> **参数:**该方法接受以下参数:
> 
> *   如果**限制**参数为正，则从追溯对象 *tb* 打印到**限制**堆栈跟踪条目(从调用者的帧开始)。否则，打印最后一个 abs(限制)条目。如果**限制**参数为无，则打印所有条目。
> *   如果**文件**参数为无，则输出到 sys.stderr 否则，它应该是一个打开的文件或类似文件的对象来接收输出。
> *   如果**链**参数为真(默认值)，那么也会打印链异常，就像解释器本身打印未处理的异常一样。
> 
> **返回:**无。

**代码:**

## 蟒蛇 3

```py
# import module
import traceback

# declaring and assigning array
A = [1, 2, 3, 4]

# exception handling
try:
    value = A[5]

except:
    # printing stack trace
    traceback.print_exc()

# out of try-except
# this statement is to show
# that program continues normally
# after an exception is handled
print("end of program")
```