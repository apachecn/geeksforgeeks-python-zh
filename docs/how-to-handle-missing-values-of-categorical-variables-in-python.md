# Python 中如何处理分类变量的缺失值？

> 原文:[https://www . geeksforgeeks . org/如何处理 python 中分类变量的缺失值/](https://www.geeksforgeeks.org/how-to-handle-missing-values-of-categorical-variables-in-python/)

机器学习是一个研究领域，它使计算机能够在没有明确编程的情况下进行学习。我们经常遇到一些数据集，其中一些值从列中丢失。当我们将机器学习模型应用于数据集时，这会导致问题。这增加了我们在训练机器学习模型时出错的机会。

我们使用的数据集是:

```
# import modules
import pandas as pd
import numpy as np

# assign dataset
df = pd.read_csv("train.csv", header=None)
df.head
```