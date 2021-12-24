# Python 退出命令:退出()，退出()，sys.exit()和 os。_exit()

> 原文:[https://www . geesforgeks . org/python-exit-commands-quit-exit-sys-exit-and-OS-_ exit/](https://www.geeksforgeeks.org/python-exit-commands-quit-exit-sys-exit-and-os-_exit/)

函数`quit()`、`exit()`、`sys.exit()`和`os._exit()`具有几乎相同的功能，因为它们引发了`SystemExit`异常，Python 解释器通过该异常退出，并且不打印堆栈追溯。
我们可以捕捉异常来拦截早期退出并执行清理活动；如果未被捕获，解释器将照常退出。

当我们用 Python 运行一个程序时，我们只需从上到下执行文件中的所有代码。脚本通常在解释器到达文件末尾时退出，但是我们也可以通过内置的退出函数调用程序显式退出。

1.  **quit()**

    它仅在导入站点模块时有效，因此不应在生产代码中使用。生产代码意味着代码正被现实世界中的目标受众使用。这个函数应该只在解释器中使用。

    它在幕后引发了系统退出异常。如果您打印它，它会给出一条信息:

    **示例:**

    ```
    # Python program to demonstrate
    # quit()

    for i in range(10):

        # If the value of i becomes 
        # 5 then the program is forced
        # to quit
        if i == 5:

            # prints the quit message
            print(quit)
            quit()
        print(i)
    ```

    **输出:**

    ```
    0
    1
    2
    3
    4
    Use quit() or Ctrl-D (i.e. EOF) to exit

    ```

2.  **exit()**

    `exit()`在`site.py`中定义，只有导入了站点模块才能工作，所以只能在解释器中使用。让 Python 更加用户友好就像`quit()`的同义词。它在打印时也会给出一条信息:

    **示例:**

    ```
    # Python program to demonstrate
    # exit()

    for i in range(10):

        # If the value of i becomes 
        # 5 then the program is forced
        # to exit
        if i == 5:

            # prints the exit message
            print(exit)
            exit()
        print(i)
    ```

    **输出:**

    ```
    0
    1
    2
    3
    4
    Use exit() or Ctrl-D (i.e. EOF) to exit

    ```

3.  **sys.exit([arg])**

    与`quit()`和`exit()`不同，`sys.exit()`被认为可以很好地用于生产代码中，因为 sys 模块总是可用的。可选参数`arg`可以是给出出口的整数或其他类型的对象。如果是整数，**零被认为是“成功终止”。**

    **注意:**字符串也可以传递给 sys.exit()方法。

    **示例–**如果年龄小于 18 岁，则停止执行的程序。

    ```
    # Python program to demonstrate
    # sys.exit()

    import sys

    age = 17

    if age < 18:

        # exits the program
        sys.exit("Age less than 18")    
    else:
        print("Age is not less than 18")
    ```

    **输出:**

    ```
    An exception has occurred, use %tb to see the full traceback.

    SystemExit: Age less than 18

    ```

4.  **os._exit(n)**

    `[os._exit()](https://www.geeksforgeeks.org/python-os-_exit-method/)`Python 中的方法用于以指定的状态退出进程，而无需调用清理处理程序、刷新 stdio 缓冲区等。

    **注:**此方法一般用于 `os.fork()`系统调用后的子进程。退出流程的标准方式是`sys.exit(n)`法。

    ```
    # Python program to explain os._exit() method  

    # importing os module   
    import os 

    # Create a child process 
    # using os.fork() method  
    pid = os.fork() 

    # pid greater than 0 
    # indicates the parent process  
    if pid > 0: 

        print("\nIn parent process") 
        # Wait for the completion  
        # of child process and     
        # get its pid and  
        # exit status indication using 
        # os.wait() method 
        info = os.waitpid(pid, 0) 

        # os.waitpid() method returns a tuple 
        # first attribute represents child's pid 
        # while second one represents 
        # exit status indication 

        # Get the Exit code  
        # used by the child process 
        # in os._exit() method 

        # firstly check if 
        # os.WIFEXITED() is True or not 
        if os.WIFEXITED(info[1]) : 
            code = os.WEXITSTATUS(info[1]) 
            print("Child's exit code:", code) 

    else : 
        print("In child process") 
        print("Process ID:", os.getpid()) 
        print("Hello ! Geeks") 
        print("Child exiting..") 

        # Exit with status os.EX_OK 
        # using os._exit() method 
        # The value of os.EX_OK is 0         
        os._exit(os.EX_OK)
    ```

    **输出:**

    ```
    In child process
    Process ID: 25491
    Hello ! Geeks
    Child exiting..

    In parent process
    Child's exit code: 0

    ```

在上述四个 exit 函数中，sys.exit()是最受欢迎的，因为 exit()和 quit()函数不能在生产代码中使用。_exit()仅适用于需要立即退出的特殊情况。