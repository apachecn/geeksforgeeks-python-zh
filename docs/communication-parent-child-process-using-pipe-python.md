# 使用 Python 中的管道进行父子进程间的通信

> 原文:[https://www . geesforgeks . org/communication-parent-child-process-use-pipe-python/](https://www.geeksforgeeks.org/communication-parent-child-process-using-pipe-python/)

先决条件–[在 Python 中创建子进程](https://www.geeksforgeeks.org/creating-child-process-using-fork-python/)
由于计算机上同时运行多个进程，因此它们之间有适当的通信是非常必要的，因为一个进程可能依赖于其他进程。进程之间的通信有多种方法。这里有一个简单的 Python 程序，使用管道方法演示父进程和子进程之间的通信。

**使用的库–**
[Python 中的操作系统模块:](https://www.geeksforgeeks.org/os-module-python-examples/)Python 中的操作系统模块提供了一种使用操作系统相关功能的方式。操作系统模块提供的功能允许您与运行 Python 的底层操作系统进行交互；无论是视窗、苹果还是 Linux。它可以作为–

```py
import os

```

**系统调用 Used–**
**[pipe()系统调用:](https://www.geeksforgeeks.org/pipe-system-call/)** 方法 pipe()创建一个 pipe，并返回一对分别可用于读写的文件描述符(r，w)。此方法**返回**一对文件描述符。

**语法–**以下是 pipe()方法的语法–

```py
os.pipe()

```

**注意–**管道只是单向通信，即我们可以使用管道，这样一个进程向管道写入，另一个进程从管道读取。

```py
# Python code to demonstrate communication
# between parent and child process using 
# python.

import os

def communication(child_writes):
    # file descriptors r, w for reading and writing
    r, w = os.pipe()

    #Creating child process using fork
    processid = os.fork()
    if processid:
        # This is the parent process
        # Closes file descriptor w
        os.close(w)
        r = os.fdopen(r)
        print ("Parent reading")
        str = r.read()
        print( "Parent reads =", str)
    else:
        # This is the child process
        os.close(r)
        w = os.fdopen(w, 'w')
        print ("Child writing")
        w.write(child_writes)
        print("Child writes = ",child_writes)
        w.close()

# Driver code        
child_writes = "Hello geeks"
communication(child_writes)

# Contributed by "Sharad_Bhardwaj".
```

**输出:**

```py
Child writing
Child writes =  Hello geeks
Parent reading
Parent reads = Hello geeks

```