# 使用 Python 中的 fork()创建子进程

> 原文:[https://www . geeksforgeeks . org/creating-child-process-using-fork-python/](https://www.geeksforgeeks.org/creating-child-process-using-fork-python/)

创建子进程并显示父进程和子进程的进程 id。

**Fork** 系统调用 use for 创建一个新的进程，称为 ***子进程*** 进程，该进程与进程(该进程称为系统调用 Fork)并发运行，该进程称为 ***父进程*** 。创建新的子进程后，两个进程都将执行 fork()系统调用之后的下一条指令。

**库使用:**
**[os](https://www.geeksforgeeks.org/os-module-python-examples/):**Python 中的 OS 模块提供了一种使用操作系统相关功能的方式。操作系统模块提供的功能允许您与运行 Python 的底层操作系统进行交互；无论是视窗、苹果还是 Linux。它可以作为–

```py
import os

```

#### 使用的系统调用:

*   **fork() :** fork()是进程创建自身副本的操作。它通常是一个系统调用，在内核中实现。*   **getpid() :** getpid() returns the process ID (PID) of the calling process.

    下面是上面实现的 Python 程序:

    ```py
    # Python code to create child process 
    import os

    def parent_child():
        n = os.fork()

        # n greater than 0  means parent process
        if n > 0:
            print("Parent process and id is : ", os.getpid())

        # n equals to 0 means child process
        else:
            print("Child process and id is : ", os.getpid())

    # Driver code
    parent_child()
    ```

    输出:

    ```py
    Child process and id is :  32523
    Parent process and id is :  32524

    ```

    **注意:**输出可以因时间、机器或工艺而异。