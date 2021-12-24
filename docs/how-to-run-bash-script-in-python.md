# 如何在 Python 中运行 bash 脚本？

> 原文:[https://www . geesforgeks . org/how-run-bash-script-in-python/](https://www.geeksforgeeks.org/how-to-run-bash-script-in-python/)

如果你使用的是任何主要的操作系统，你就是在间接与 bash 交互。如果您运行的是 Ubuntu、Linux Mint 或任何其他 Linux 发行版，那么每次使用终端时，您都在与 bash 进行交互。假设您已经编写了需要从 python 代码中调用的 bash 脚本。设计用于产生新流程并与之通信的模块有一个名称**子流程**。

让我们考虑这样一个简单的例子，给出一个推荐的调用子流程的方法。作为一个参数，您必须传递您想要调用的命令及其参数，所有这些参数都包装在一个列表中。

## 蟒 3

```
import subprocess

# execute command
subprocess.run(["echo", "Geeks for geeks"])
```