# 在 Python 中向 Anaconda 环境添加包

> 原文:[https://www . geesforgeks . org/python-add-packages-to-anaconda-environment/](https://www.geeksforgeeks.org/python-add-packages-to-anaconda-environment/)

让我们看看一些可以用来将包安装到 [Anaconda](https://www.geeksforgeeks.org/set-opencv-anaconda-environment/) 环境的方法。

有许多方法可以将预构建的包添加到 anaconda 环境中。那么，让我们看看如何在蟒蛇中指引路径并安装它们。

**使用** ***pip*** **命令:**

1.  以管理员身份打开 Anaconda 命令提示符
2.  使用 **cd\** 从设置的目录或路径中出来。
3.  运行 **pip 安装**命令。

```py
pip install numpy
pip install scikit-learn
```

**使用** ***git*** **:**

1.  下载 *git* 文件
2.  在某个目录中克隆或下载 git 集线器文件。
3.  以管理员身份打开 Anaconda 命令提示符。
4.  使用 cd C:\Users\…定位下载的站点。
5.  然后运行 **pip 安装程序。**

**使用** ***轮*** **:**

1.  下载**轮**包。
2.  下载二进制文件或。真实网站上的文件。
3.  以管理员身份打开 Anaconda 命令提示符。
4.  使用 cd C:\Users\…定位下载的站点。
5.  然后运行 pip install __。whl

**使用*****Conda forge*****命令:**
这种类型的安装会保证包会下载到系统中。因为这种类型的安装解决了环境、包-包冲突等问题。

1.  将相关包自升级到下载包。
2.  以管理员身份打开 Anaconda 命令提示符。
3.  然后运行 conda install -c conda-forge ___

```py
conda install -c conda-forge opencv 
```