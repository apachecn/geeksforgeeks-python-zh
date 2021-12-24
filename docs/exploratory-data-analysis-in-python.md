# Python 中的探索性数据分析

> 原文:[https://www . geesforgeks . org/explorive-data-analysis-in-python/](https://www.geeksforgeeks.org/exploratory-data-analysis-in-python/)

## 什么是探索性数据分析？

EDA 是数据分析下的一种现象，用于更好地理解数据方面，如:
–数据的主要特征
–变量以及变量之间的关系
–确定哪些变量对我们的问题很重要
我们将研究各种探索性数据分析方法，如:

*   描述性统计，这是一种对我们正在处理的数据集进行简要概述的方式，包括样本的一些度量和特征
*   分组数据【以分组的*基本分组】*
*   方差分析，方差分析，这是一种将一组观察值中的变化分成不同部分的计算方法。
*   相关和相关方法

我们将使用的数据集是子投票数据集，您可以在 python 中将其导入为:

## 蟒蛇 3

```py
import pandas as pd
Df = pd.read_csv("https://vincentarelbundock.github.io / Rdatasets / csv / car / Child.csv")
```