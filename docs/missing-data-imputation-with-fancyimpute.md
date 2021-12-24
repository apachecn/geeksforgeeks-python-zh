# 使用 fancyimpute 进行缺失数据插补

> 原文:[https://www . geeksforgeeks . org/missing-data-插补-with-fanjimpute/](https://www.geeksforgeeks.org/missing-data-imputation-with-fancyimpute/)

在真实世界的数据集中，总会有一些数据丢失。这主要与数据是如何收集的有关。缺失数据在创建预测模型中起着重要的作用，因为有些算法在缺失数据集上表现不佳。

### fancyinput

fancyimpute 是一个缺失数据插补算法库。Fancyimpute 使用机器学习算法来估算缺失值。Fancyimpute 使用所有列来估算缺失的值。有两种方法可以估算缺失的数据:使用 fanchimpte

1.  KNN or k nearest neighbor
2.  MICE or through chain equation

多重估算

### k-最近邻

为了填充缺失值，KNN 找出所有特征中相似的数据点。然后用所有点的平均值来填充缺失的值。

T2T4

```
import pandas as pd
import numpy as np
# importing the KNN from fancyimpute library
from fancyimpute import KNN

df = pd.DataFrame([[np.nan, 2, np.nan, 0],
                   [3, 4, np.nan, 1],
                   [np.nan, np.nan, np.nan, 5],
                   [np.nan, 3, np.nan, 4],
                   [5,      7,  8,     2],
                   [2,      5,  7,     9]],
                  columns = list('ABCD'))

# printing the dataframe
print(df)

# calling the KNN class
knn_imputer = KNN()
# imputing the missing value with knn imputer
df = knn_imputer.fit_transform(df)

# printing dataframe
print(df)
```

T5

### 输出:

```
    A    B    C  D
0  NaN  2.0  NaN  0
1  3.0  4.0  NaN  1
2  NaN  NaN  NaN  5
3  NaN  3.0  NaN  4
4  5.0  7.0  8.0  2
5  2.0  5.0  7.0  9
Imputing row 1/6 with 2 missing, elapsed time: 0.001
[[3.23556938 2\.         7.75630267 0.]
 [3\.         4\.         7.825      1.]
 [3.67647071 3.46386587 7.64000033 5.]
 [3.35514006 3\.         7.59183674 4.]
 [5\.         7\.         8\.         2.]
 [2\.         5\.         7\.         9.]]

```

### 链式方程多重插补:

MICE 使用多重插补，而不是单一插补，这导致统计不确定性。MICE 对样本数据进行多元回归，取平均值

## 

```
import pandas as pd
import numpy as np
# importing the MICE from fancyimpute library
from fancyimpute import IterativeImputer

df = pd.DataFrame([[np.nan, 2, np.nan, 0],
                   [3, 4, np.nan, 1],
                   [np.nan, np.nan, np.nan, 5],
                   [np.nan, 3, np.nan, 4],
                   [5,      7,  8,     2],
                   [2,      5,  7,     9]],
                  columns = list('ABCD'))

# printing the dataframe
print(df)

# calling the  MICE class
mice_imputer = IterativeImputer()
# imputing the missing value with mice imputer
df = mice_imputer.fit_transform(df)

# printing dataframe
print(df)
```

#### 输出

```
    A    B    C   D
0  NaN  2.0  NaN  0
1  3.0  4.0  NaN  1
2  NaN  NaN  NaN  5
3  NaN  3.0  NaN  4
4  5.0  7.0  8.0  2
5  2.0  5.0  7.0  9
[[3.27262261 2\.         7.9809332  0 ]
 [3\.         4\.         7.9193547  1.]
 [2.91717117 4.35730239 7.47523962 5.]
 [2.77722048 3\.         7.53760743 4.]
 [5\.         7\.         8\.         2.]
 [2\.         5\.         7\.         9.]]

```