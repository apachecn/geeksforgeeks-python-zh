# Python |使用 KNNimputer()进行插补

> 原文:[https://www . geeksforgeeks . org/python-插补-使用-knnimputer/](https://www.geeksforgeeks.org/python-imputation-using-the-knnimputer/)

**KNNimputer** 是一个 scikit-learn 类，用于填充或预测数据集中缺失的值。这是一种更有用的方法，它基于 KNN 算法的基本方法，而不是用平均值或中值填充所有值的简单方法。在这种方法中，我们指定与缺失值的距离，也称为 K 参数。缺失值将参照相邻值的平均值进行预测。

它由 **KNNimputer()** 方法实现，该方法包含以下参数:

> **n_neighbors:** 更接近缺失值的数据点数量。
> **度量:**用于搜索的距离度量。
> 值–{ nan _ euclidean。可调用}默认–nan _ euclidean
> **权重:**确定应该在什么基础上处理相邻值
> 值-{uniform，distance，callable}默认- uniform。

**代码:Python 代码说明 KNNimputor 类**

```py
# import necessary libraries
import numpy as np
import pandas as pd

# import the KNNimputer class
from sklearn.impute import KNNImputer

# create dataset for marks of a student
dict = {'Maths':[80, 90, np.nan, 95], 
        'Chemistry': [60, 65, 56, np.nan], 
        'Physics':[np.nan, 57, 80, 78],
       'Biology' : [78,83,67,np.nan]}

# creating a data frame from the list 
Before_imputation = pd.DataFrame(dict)
#print dataset before imputaion
print("Data Before performing imputation\n",Before_imputation)

# create an object for KNNImputer
imputer = KNNImputer(n_neighbors=2)
After_imputation = imputer.fit_transform(Before_imputation)
# print dataset after performing the operation
print("\n\nAfter performing imputation\n",After_imputation)
```

**输出:**

```py
Data Before performing imputation
    Maths  Chemistry  Physics  Biology
0   80.0       60.0      NaN     78.0
1   90.0       65.0     57.0     83.0
2    NaN       56.0     80.0     67.0
3   95.0        NaN     78.0      NaN

After performing imputation
 [[80\.  60\.  68.5 78\. ]
 [90\.  65\.  57\.  83\. ]
 [87.5 56\.  80\.  67\. ]
 [95\.  58\.  78\.  72.5]]

```

**注意:**变换后的数据变成 numpy 数组。