# 在 Windows 和 Linux 中创建 Python 虚拟环境

> 原文:[https://www . geesforgeks . org/creating-python-virtual-environment-windows-Linux/](https://www.geeksforgeeks.org/creating-python-virtual-environment-windows-linux/)

虚拟环境是一个 python 环境，它是 Python 的一个独立的工作副本，允许您在不影响其他项目的情况下处理特定的项目
所以基本上它是一个工具，支持 Python 的多个并行安装，每个项目一个。

**在 Linux 中创建虚拟环境**

如果 pip 不在您的系统中

```py
$ sudo apt-get install python-pip
```

然后安装 virtualenv

```py
$ pip install virtualenv
```

现在检查您的安装

```py
$ virtualenv --version
```

现在创建一个虚拟环境，

```py
$ virtualenv virtualenv_name
```

执行此命令后，将创建一个名为 **virtualenv_name** 的文件夹。你可以给它起任何名字。如果要为特定的 python 版本创建 virtualenv，请键入

```py
$ virtualenv -p /usr/bin/python3 virtualenv_name
```

或者

```py
$ virtualenv -p /usr/bin/python2.7 virtualenv_name
```

现在我们只需要使用命令激活它

```py
$ source virtualenv_name/bin/activate
```

现在，您处于 Python 虚拟环境中

您可以使用停用

```py
$ deactivate
```

**在 Windows 中创建 Python virtualenv**

如果你的系统中安装了 python，那么 pip 就派上用场了。
那么简单的步骤是:
1)安装 virtualenv 使用

```py
 > pip install virtualenv 
```

2)现在无论你在哪个目录中，下面这一行将在那里创建一个虚拟目录

```py
 > virtualenv myenv
```

这里你也可以给它起任何名字。

3)现在，如果您是同一目录，则键入:

```py
 > myenv\Scripts\activate
```

您也可以明确指定您的路径。

类似于 Linux，你可以像

```py
$ deactivate
```