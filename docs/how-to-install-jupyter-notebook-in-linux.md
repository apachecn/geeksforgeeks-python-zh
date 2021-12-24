# 如何在 Linux 中安装 Jupyter 笔记本？

> 原文:[https://www . geesforgeks . org/how-install-jupyter-notebook in-Linux/](https://www.geeksforgeeks.org/how-to-install-jupyter-notebook-in-linux/)

Jupyter Notebook 是一个开源网络应用程序，允许您创建和共享包含实时代码、公式、可视化和叙事文本的文档。用途包括数据清理和转换、数值模拟、统计建模、数据可视化、机器学习等等。

Jupyter 支持 40 多种不同的编程语言， [Python](https://www.geeksforgeeks.org/python-language-introduction/) 就是其中之一。Python 是安装 Jupyter 笔记本本身的要求(Python 3.3 或更高版本，或 Python 2.7)。

Jupyter 笔记本可以通过以下两种方式安装:

*   **使用 Anaconda:**
    使用 Anaconda 发行版安装 Python 和 Jupyter，该发行版包括 Python、Jupyter Notebook 和其他用于科学计算和数据科学的常用软件包。安装 Anaconda，要经过[如何在 Linux 上安装 Anaconda？](https://www.geeksforgeeks.org/how-to-install-anaconda-on-linux/)并按照提供的说明操作。
*   **使用 PIP:**
    使用 **PIP 包管理器**安装 Jupyter，用于安装和管理用 Python 编写的软件包/库。要安装 pip，请通过[如何在 Linux 中安装 PIP？](https://www.geeksforgeeks.org/how-to-install-pip-in-linux/)并遵循提供的说明。

### 使用 Anaconda 安装 Jupyter 笔记本:

Anaconda 是一个开源软件，包含 Jupyter、spyder 等，用于大型数据处理、数据分析、重型科学计算。Anaconda 为 R 和 python 编程语言工作。python 使用 spyder(Anaconda 的子应用程序)。python 的 Opencv 将在 spyder 中工作。软件包版本由名为 conda 的软件包管理系统管理。

要使用 Anaconda 安装 Jupyter，只需按照以下说明操作:

*   **发射巨蟒领航员:**
    ![Anaconda Navigator Linux](img/7991893838818a017cc80f919860001f.png)
*   **点击安装 Jupyter 笔记本按钮:**
    ![Clicking Installation button](img/566589bba3e1c2cb1123b0aa59a21da4.png)
*   **开始安装:**
    ![Beginning Installation process](img/2f27a571c3915983d1477f8b85b29f82.png)
*   **装载包裹:**
    ![Loading Packages to install](img/7ed33399ce1a66698bfd1f46e8e09471.png)
*   **安装完毕:**
    ![Finishing Installation Process](img/4d4871f411266a619e11bca37f2e1edd.png)

**发射 Jupyter:**
![Launching Jupyter on Linux](img/e8be21ae845a8b4b29e4ec5ac89eb871.png)
![Jupyter Home Window](img/855816be91799435a9dd79fd6b224dd1.png)

### 使用 pip 安装 Jupyter 笔记本:

**PIP** 是一个包管理系统，用于安装和管理用 Python 编写的软件包/库。这些文件存储在一个被称为 Python 包索引(PyPI)的大型“在线存储库中”。
pip 使用 PyPI 作为包及其依赖项的默认来源。

要使用 pip 安装 Jupyter，我们需要首先检查 pip 是否在我们的系统中更新。使用以下命令更新 pip:

```
python3 -m pip install --upgrade pip
```

![Updating pip before installation](img/f8b0079a332941cac6156021e06ea4ac.png)

更新 pip 版本后，按照下面提供的说明安装 Jupyter:

*   **命令安装 Jupyter:**

    ```
    pip3 install Jupyter

    ```

*   **开始安装:**
    ![Beginning with the Installation](img/6498d1d7ae4d79dae0e8706cba8a1506.png)
*   **收集文件和数据:**
    ![Collecting Files to be downloaded](img/f43fd0758e8f938f8ae0dc1ec569a0ad.png)
*   **下载套餐:**
    ![Downloading Packages](img/12613fdac96ec9ff0949283350e7af6f.png)
*   **运行安装:**
    ![Finishing Installation](img/f20dc24685cfdc48ff9462fa318cdb3b.png)
*   **安装完毕:**
    ![Installing files and packages](img/2e71f023aa8d2240ff3e3e0302edaaa6.png)

**启动 Jupyter:**
使用以下命令使用命令行启动 Jupyter:

```
jupyter notebook
```

![Command to Launch Jupyter](img/6b9719559b4010f02629edb64359896c.png)
![Jupyter Home Window in Linux](img/855816be91799435a9dd79fd6b224dd1.png)