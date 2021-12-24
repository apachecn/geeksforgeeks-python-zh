# 从头开始实施 AdaBoost 算法

> 原文:[https://www . geeksforgeeks . org/从头开始实现-AdaBoost-算法/](https://www.geeksforgeeks.org/implementing-the-adaboost-algorithm-from-scratch/)

AdaBoost 模型属于一类集成机器学习模型。从“集合”这个词的字面意思来看，我们很容易对这个模型的工作原理有更好的直觉。集成模型承担了组合不同模型的责任，并在以后产生一个高级/更精确的元模型。与对应的模型相比，这个元模型在预测方面具有相对较高的准确性。我们已经在文章[集成分类器|数据挖掘](https://www.geeksforgeeks.org/ensemble-classifier-data-mining/)中了解了这些集成模型的工作。

AdaBoost 算法属于集成增强技术，正如所讨论的，它组合多个模型以产生更精确的结果，这分两个阶段完成:

1.  Allow multiple weak learners to learn on training data.
2.  These models are combined to generate meta-model, which aims to solve the errors performed by a single weak learner.

**注:**更多信息请参考[助推系综模型](https://www.geeksforgeeks.org/boosting-in-machine-learning-boosting-and-adaboost/)

在本文中，我们将学习 AdaBoost 分类器在数据集上的实际实现。

在这个问题中，我们给出了一个包含 3 种花和这些花的特征的数据集，例如-萼片长度、萼片宽度、花瓣长度和花瓣宽度，并且我们必须将这些花分类成这些种类。数据集可以从[这里](https://www.shortto.com/flower-dataset)下载

让我们从导入完成分类任务所需的重要库开始:

## 【Python】

```
import pandas as pd
import numpy as np
from sklearn.model_selection import train_test_split
from sklearn.ensemble import AdaBoostClassifier
import warnings
warnings.filterwarnings("ignore")
```

导入库后，我们将使用熊猫 *read_csv* 方法加载数据集，如下所示:

## Python

```
# Reading the dataset from the csv file
# separator is a vertical line, as seen in the dataset
data = pd.read_csv("Iris.csv")

# Printing the shape of the dataset
print(data.shape)
```

```
(150, 6)
```

我们可以看到我们的数据集包含 150 行和 6 列。让我们使用 *head()* 方法看一下我们在数据集中的实际内容如下:

## Python

```
data.head()
```