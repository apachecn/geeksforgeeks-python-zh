# Python 中 Dask 的介绍

> 原文:[https://www . geesforgeks . org/introduction-to-dask-in-python/](https://www.geeksforgeeks.org/introduction-to-dask-in-python/)

Dask 是一个支持 python 并行计算的库。它提供了如下功能-

1.  针对交互式计算工作负载进行优化的动态任务调度
2.  dask 的大数据集合扩展了 NumPy、Pandas 等常用接口。

## **为什么是 Dask？**

大部分的大数据分析将使用熊猫、NumPy 来分析大数据。所有提到的包都支持各种各样的计算。但是当数据集不适合内存时，这些包将无法扩展。达斯克来了。当**数据集不“适合内存”时，dask 将数据集扩展为“适合磁盘”**。Dask 允许我们根据数据集的大小轻松扩展到集群或缩小到单台机器。

#### 装置

要安装该模块，请在终端中键入以下命令–

```
python -m pip install "dask[complete]" 
```

让我们看一个比较 dask 和熊猫的例子。要下载以下示例中使用的数据集，请单击此处的。

**1。Pandas Performance:** 使用 pd.read_csv()读取数据集

## 蟒蛇 3

```
import pandas as pd

%time temp = pd.read_csv('dataset.csv',
                          encoding = 'ISO-8859-1')
```

**输出:**

> 中央处理器时间:用户 619 毫秒，系统:73.6 毫秒，总计:692 毫秒
> 
> 挂壁时间:705 毫秒

**2。Dask 性能:**使用 dask.dataframe.read_csv 读取数据集

## 蟒蛇 3

```
import dask.dataframe as dd

%time df = dd.read_csv("dataset.csv", 
                        encoding = 'ISO-8859-1')
```

**输出:**

> 中央处理器时间:用户 21.7 毫秒，系统:938 秒，总时间:22.7 毫秒
> 
> 挂壁时间:23.2 毫秒

现在可能会出现一个问题，在 dask 之前，使用熊猫处理的数据集有多大？管理大熊猫的大数据集很少有技巧。

1.  大熊猫 read_csv 分块大小参数的应用
2.  读取 csv 文件时仅使用所需的列

在大多数情况下，当使用熊猫读取大数据集时，将遵循上述技术。但在某些情况下，上述内容在 dask 发挥重要作用时可能没有用。

## dask 的局限性

dask 有一定的局限性。

1.  Dask 不能在单个任务中并行化。
2.  作为一个分布式计算框架，dask 支持远程执行任意代码。因此 dask 工作人员应该只托管在可信网络中。