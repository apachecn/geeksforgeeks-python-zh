# python 中如何清屏？

> 原文:[https://www.geeksforgeeks.org/clear-screen-python/](https://www.geeksforgeeks.org/clear-screen-python/)

大多数时候，在使用 python interactive shell/terminal(而不是控制台)时，我们最终会得到一个混乱的输出，并且出于某种原因想要清除屏幕。
在交互式外壳/终端中，我们可以简单地使用

```py
ctrl+l
```

但是，如果我们想在运行 python 脚本时清除屏幕，该怎么办。
可惜没有内置关键字或函数/方法来清屏。所以，我们自己做。

我们可以使用 ANSI 转义序列，但这些是不可移植的，可能不会产生所需的输出。

```py
print(chr(27)+'[2j')
print('\033c')
print('\x1bc')
```

所以，我们在脚本中要做的是:

> 1.  From os import system.
> 2.  Define functions.
> 3.  Make system calls with' clear' in Linux and' cls' in Windows as parameters.
> 4.  Store the return value in underline or any variable you want (underline is used because python shell always stores its final output in underline).
> 5.  Call the function we defined.

```py
# import only system from os
from os import system, name

# import sleep to show output for some time period
from time import sleep

# define our clear function
def clear():

    # for windows
    if name == 'nt':
        _ = system('cls')

    # for mac and linux(here, os.name is 'posix')
    else:
        _ = system('clear')

# print out some text
print('hello geeks\n'*10)

# sleep for 2 seconds after printing output
sleep(2)

# now call function we defined above
clear()
```

注意:您也只能“导入操作系统”而不是“从操作系统导入系统”，但是您必须将系统(“清除”)更改为操作系统。系统(“清除”)。

实现这一点的另一种方法是使用子流程模块。

```py
# import call method from subprocess module
from subprocess import call

# import sleep to show output for some time period
from time import sleep

# define clear function
def clear():
    # check and make call for specific operating system
    _ = call('clear' if os.name =='posix' else 'cls')

print('hello geeks\n'*10)

# sleep for 2 seconds after printing output
sleep(2)

# now call function we defined above
clear()
```