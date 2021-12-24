# 如何在 python 中生成字节码文件？

> 原文:[https://www . geesforgeks . org/generate-byte-code-file-python/](https://www.geeksforgeeks.org/generate-byte-code-file-python/)

每当 Python 脚本编译时，它都会自动生成一个被称为字节码的编译代码。字节码实际上并没有被解释成机器代码，除非有一些奇特的实现，比如[pypypy](https://en.wikipedia.org/wiki/PyPy)。

字节码被加载到 Python 运行时，并由虚拟机解释，虚拟机是一段代码，它读取字节码中的每个指令，并执行指示的任何操作。

字节码自动创建在与相同的目录中。py 文件，当第一次导入 python 的一个*模块*时，或者当源文件比当前编译的文件更新时。下一次，当程序运行时，python 解释器使用这个文件跳过编译步骤。

运行脚本不被认为是**导入**，否。将创建 pyc 文件。例如，让我们编写一个脚本文件 **abc.py** 来导入另一个模块 **xyz.py** 。现在运行 **abc.py** 文件， **xyz.pyc** 会因为 xyz 被导入而被创建，但是 **abc.pyc** 文件不会因为 **abc.py** 没有被导入而被创建。

但是存在一个内置的 **py_compile** 和 **compileall** 模块和命令，它们便于创建。pyc 文件。

1.  Using **py_compile.compile** function: The *py_compile* module can manually compile any module. One way is to use the py_compile.compile function in that module interactively:

    ```
    >>> import py_compile
    >>> py_compile.compile('abc.py')

    ```

    这将写。pyc 到与 abc.py 相同的位置。

2.  使用 **py_compile.main()** 函数:一次编译几个文件。

    ```
    >>> import py_compile
    >>> py_compile.main(['File1.py','File2.py','File3.py'])

    ```

3.  使用 **compileall.compile_dir()** 函数:它编译提供的目录中的每个 python 文件。

    ```
    >>> import compileall
    >>> compileall.compile_dir(directoryname)

    ```

4.  Using **py_compile** in Terminal:

    ```
    $ python -m py_compile File1.py File2.py File3.py ...

    ```

    或者，对于文件的交互式编译

    ```
    $ python -m py_compile -
      File1.py
      File2.py
      File3.py
       .
       .
       .

    ```

5.  在终端中使用**编译所有**:这个命令会自动递归进入子目录并制作。它找到的所有 python 文件的 pyc 文件。

    ```
    $ python -m compileall 

    ```

**注意**:**compilell**和 **py_compile** 模块是 python 标准库的一部分，使用它不需要额外安装任何东西。

**参考文献:**
1。[https://docs.python.org/3/library/py_compile.html](https://docs.python.org/3/library/py_compile.html)T5【2】。[https://docs.python.org/2/library/compileall.html](https://docs.python.org/2/library/compileall.html)T8】3。[Effebot](http://effbot.org/pyfaq/how-do-i-create-a-pyc-file.htm)

本文由 [Shubham Bansal](https://www.quora.com/profile/Shubham-Bansal-209) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。