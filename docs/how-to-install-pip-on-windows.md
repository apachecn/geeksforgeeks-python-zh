# 如何在 Windows 上安装 PIP？

> 原文:[https://www . geesforgeks . org/how-install-pip-on-windows/](https://www.geeksforgeeks.org/how-to-install-pip-on-windows/)

**先决条件:** [Python 语言介绍](https://www.geeksforgeeks.org/python-language-introduction/)

在开始介绍如何在 Windows 上为 Python 安装 pip 之前，我们先来看一下 Python 的基本介绍。 [Python](https://www.geeksforgeeks.org/python-programming-language/) 是一种广泛使用的通用高级编程语言。Python 是一种编程语言，可以让您快速工作并更高效地集成系统。

**PIP** 是一个包管理系统，用于安装和管理用 Python 编写的软件包/库。这些文件存储在一个被称为 Python 包索引(PyPI)的大型“在线存储库中”。

pip 使用 PyPI 作为包及其依赖项的默认来源。所以无论何时你输入:

```
pip install package_name
```

pip 将在 PyPI 上查找该包，如果找到，它将在您本地系统上下载并安装该包。

### 下载并安装 pip:

通过以下步骤，可以使用命令行下载和安装 pip:

*   下载 [**get-pip.py**](https://bootstrap.pypa.io/get-pip.py) 文件，并将其存储在安装 python 的同一个目录中。
    ![Downloading and storing get-pip file](img/1114218ca28a90b838ad7b0ee4fa5224.png)
*   将命令行中目录的当前路径更改为上述文件所在目录的路径。
    ![Changing directory path](img/fa96dbe7a24065aa2dbc360b59f9a5b9.png)
*   Run the command given below:

    ```
    python get-pip.py
    ```

    并等待安装过程。
    ![Executing the command](img/7c4105496e056e7832b20b626412d426.png)

*   瞧啊。pip 现已安装在您的系统上。

### 安装过程的验证:

通过对 pip 执行版本检查，可以轻松验证 pip 是否已正确安装。只需转到命令行并执行以下命令:

```
pip -V
```

![Verification of pip](img/34ad4224f5102abd1c856b42b0e052af.png)