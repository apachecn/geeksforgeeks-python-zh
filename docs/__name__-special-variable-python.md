# __ Python 中的名称 _ _(一个特殊变量)

> 原文:[https://www . geesforgeks . org/_ _ name _ _-special-variable-python/](https://www.geeksforgeeks.org/__name__-special-variable-python/)

由于 python 中没有 main()函数，当运行 Python 程序的命令被提供给解释器时，处于 0 级缩进的代码将被执行。然而，在此之前，它将定义一些特殊的变量。__name__ 就是这样一个特殊变量。如果源文件作为主程序执行，解释器将 __name__ 变量设置为值“__main__”。如果此文件正从另一个模块导入，则 __name__ 将被设置为该模块的名称。
**__name__ 是一个内置变量，计算结果为当前模块的名称。**因此，它可以通过与 if 语句组合来检查当前脚本是自己运行还是导入到其他地方，如下所示。

考虑两个独立的文件文件 1 和文件 2。

```
# File1.py 

print ("File1 __name__ = %s" %__name__) 

if __name__ == "__main__": 
    print ("File1 is being run directly")
else: 
    print ("File1 is being imported")
```

```
# File2.py 

import File1 

print ("File2 __name__ = %s" %__name__) 

if __name__ == "__main__": 
    print ("File2 is being run directly")
else: 
    print ("File2 is being imported")
```

```
Now the interpreter is given the command to run File1.py.
python File1.py
Output :
File1 __name__ = __main__
File1 is being run directly

And then File2.py is run.
python File2.py
Output :
File1 __name__ = File1
File1 is being imported
File2 __name__ = __main__
File2 is being run directly

```

如上所述，当直接运行 File1.py 时，解释器将 __name__ 变量设置为 __main__ 并且当通过导入运行 File2.py 时，将 __name__ 变量设置为 python 脚本的名称，即 File1。因此，可以说 **if __name__ == "__main__ "是当使用类似 python File1.py.** 的命令从命令行运行脚本时运行的程序部分

本文由 **Harshit Agrawal** 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。