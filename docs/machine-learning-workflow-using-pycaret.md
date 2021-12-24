# 使用 Pycaret 的机器学习工作流

> 原文:[https://www . geesforgeks . org/机器学习-工作流-使用-pycaret/](https://www.geeksforgeeks.org/machine-learning-workflow-using-pycaret/)

PyCaret 是一个开源的机器学习库，简单易用。它帮助您从数据准备的开始到模型分析和部署的结束。此外，它本质上是几个机器学习库和框架的 python 包装器，如 **scikit-learn、spaCy** 等，它还支持复杂的机器学习算法，这些算法的调整和实现非常繁琐。

![](img/4528690409d6c311e3fbec1c2bb15fd5.png)

那么为什么要用 **Pycaret** 。嗯，有很多原因，让我给你解释几个。**第一个** Pycaret 是一个低代码库，它让你在解决业务问题时更有效率。**其次** Pycaret 只需一行代码就可以完成数据预处理和特征工程，而在现实中却非常耗时。**第三** Pycaret 允许您比较不同的机器学习模型，并非常容易地微调您的模型。嗯，还有很多其他的优点，但就目前而言，坚持下去。

#### 装置

```py
pip install pycaret
```

如果你用的是 Azure 笔记本或者谷歌可乐

```py
!pip install pycaret
```

在本文中，我们将在 Iris 分类数据集上使用 pycaret，您可以在此处下载数据集[https://archive.ics.uci.edu/ml/datasets/iris](https://archive.ics.uci.edu/ml/datasets/iris)

让我们从导入所需的库开始。

## 蟒蛇 3

```py
# importing required libraries
# for reading and manipulating data
import numpy as np
import pandas as pd
```

使用**熊猫**库读取数据集

## 蟒蛇 3

```py
# reading the data from csv file
iris_classification = pd.read_csv('Iris.csv')

# viewing top 5 rows of data
iris_classification.head(5)
```