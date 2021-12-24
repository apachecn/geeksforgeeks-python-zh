# Python 中 Vaex 的介绍

> 原文:[https://www . geesforgeks . org/introduction-to-vaex-in-python/](https://www.geeksforgeeks.org/introduction-to-vaex-in-python/)

处理大数据在今天已经变得非常普遍，因此我们需要一些库来帮助我们处理系统(即台式机、笔记本电脑)中的大数据，这些库可以即时执行代码，并且内存使用率低。

**Vaex** 是一个 Python 库，它帮助我们实现了这一点，并使处理大型数据集变得超级容易。特别是对于**懒惰的核心外数据帧**(类似熊猫)。它可以在大的表格数据集上快速可视化、浏览和执行计算，并且占用最少的内存。

## 安装:

使用 Conda:

```
conda install -c conda-forge vaex
```

使用 pip:

```
pip install --upgrade vaex
```

## 为什么是 Vaex？

Vaex 通过惰性计算、虚拟列、内存映射、零内存复制策略、高效数据清理等，帮助我们高效、快速地处理大型数据集。Vaex 有高效的算法，它强调聚合数据属性，而不是查看单个样本。它能够克服其他库的几个缺点(比如:-熊猫)。所以，让我们探索瓦克斯:-

### **阅读表现**

对于大型表格数据，Vaex 的读取性能比熊猫快得多。让我们通过用两个库导入相同大小的数据集来进行分析。[链接到数据集](https://drive.google.com/drive/folders/11RsDNUTivoOdTio2Khi3USUPiy5iNvx2?usp=sharing)

**熊猫阅读表演** :

## 蟒蛇 3

```
import pandas as pd
%time df_pandas = pd.read_csv("dataset1.csv")
```

**输出:**

```
Wall time: 1min 8s
```

**Vaex 的读取性能**:(我们使用 vaex.open 读取 Vaex 中的数据集)

## python 3

```
import vaex
%time df_vaex = vaex.open("dataset1.csv.hdf5")
```