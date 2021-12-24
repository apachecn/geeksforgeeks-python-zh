# Python 退出处理程序(atexit)

> 原文:[https://www.geeksforgeeks.org/python-exit-handlers-atexit/](https://www.geeksforgeeks.org/python-exit-handlers-atexit/)

**atextit** 是 python 中的一个模块，包含两个功能`register()`和`unregister()`。该模块的主要作用是在解释器终止时执行清理。在解释器终止时，注册的函数会自动执行。每当程序被非 Python 处理的信号杀死时，当调用`os.exit()`时，或者检测到 Python 致命内部错误时，通过该模块注册的函数不会被执行。

*   **register():** Register function takes a function as an argument that is to be executed at interpreter termination. If there are multiple functions passed as arguments e.g. (fun1(), fun2()..) then there execution will be in reverse order (…fun2(), fun1()). The execution occurs in last in first out (LIFO) concept.

    > **语法:** atexit.register(fun、*args、**kwargs)
    > 
    > **参数:**首先提到函数名，然后传递该函数的任何参数。参数用“，”分隔。
    > 
    > **返回:**这个函数返回被调用的乐趣，因此可以跟踪调用。

    **注意:**这个功能也可以作为装饰器使用。

    **#例 1:**

    ```

    # Python program to demonstrate
    # atexit module

    import atexit

    names = ['Geeks', 'for', 'Geeks']

    def hello(name):
        print (name)

    for name in names:

        # Using register()
        atexit.register(hello, name)
    ```

    **输出:**

    ```
    Geeks
    for
    Geeks

    ```

    **#例 2:** 使用寄存器作为装饰器

    ```
    # Python program to demonstrate
    # atexit module

    import atexit

    # Using register() as a decorator
    @atexit.register
    def goodbye():
        print("GoodBye.")
    ```

    **输出:**

    ```
    GoodBye.

    ```

*   **unregister():** The `unregister()` function removes the specified fun from the functions defined in the program. It provides a surety that the fun will not be called when the interpreter terminates.

    > **语法:** atexit.unregister(有趣)
    > 
    > **参数:**函数可以包含也可以不包含任何参数。如果有礼物的话，那就要指定有趣的名字。
    > 
    > **返回:**不返回。

    **示例:**

    ```
    # Python program to demonstrate
    # atexit module

    import atexit

    names = ['Geeks', 'for', 'Geeks']

    def hello(name):
        print (name)

    for name in names:

        # Using unregister() 
        atexit.unregister(hello) 
    ```

    **输出:**

    ```
    No Output

    ```