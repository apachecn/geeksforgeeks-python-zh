# 如何接近机器学习项目:分步指导

> 原文:[https://www . geeksforgeeks . org/如何一步一步地接近机器学习项目指南/](https://www.geeksforgeeks.org/how-to-approach-a-machine-learning-project-a-step-wise-guidance/)

本文将提供一个初学者应该如何进行[机器学习](https://www.geeksforgeeks.org/machine-learning/)项目的基本步骤，并描述所涉及的基本步骤。在问题中，我们将重点讨论鸢尾花的分类。您可以在这里了解数据集[。](https://archive.ics.uci.edu/ml/datasets/Iris)

很多老师和网站都拿这个问题来演示机器学习项目中涉及的各种细微差别，因为–

1.  All attributes are **numbers** and all attributes are in the same proportion and unit.
2.  The problem at hand is a **classification problem** , which gives us an option to explore many evaluation indexes.
3.  The involved data set is a **small and clean** , so it can be easily handled.

我们演示了以下步骤，并对它们进行了相应的描述。

**第一步:导入需要的库**

## python 3

```py
import pandas as pd
from pandas.plotting import scatter_matrix
import matplotlib.pyplot as plt
from sklearn import model_selection
from sklearn.metrics import classification_report, confusion_matrix, accuracy_score
from sklearn.linear_model import LogisticRegression
from sklearn.tree import DecisionTreeClassifier
from sklearn.neighbors import KNeighborsClassifier
```

**第二步:加载数据**

## python 3

```py
# dataset (csv file) path
url = "https://raw.githubusercontent.com /jbrownlee/Datasets/master/iris.csv"

# selectng necessary feature
features = ['sepal-length', 'sepal-width', 'petal-length', 'petal-width', 'class']

# reading the csv
data = pd.read_csv(url, names = features)
```

**第三步:汇总数据**

该步骤通常包括以下步骤-

**a)偷看数据**

## python 3

```py
data.head()
```