# 使用 GridSearchCV 和 KerasClassifier 进行超参数调整

> 原文:[https://www . geeksforgeeks . org/hyperparameter-tuning-using-gridsearchcv-and-kerasclassifier/](https://www.geeksforgeeks.org/hyperparameter-tuning-using-gridsearchcv-and-kerasclassifier/)

[超参数调整](https://www.geeksforgeeks.org/ml-hyperparameter-tuning/)是通过调整神经网络的参数来提高模型的效率。一些 sci kit-learn API，如 GridSearchCV 和 RandomizedSearchCV，用于执行超参数调整。

在本文中，您将学习如何使用 GridSearchCV 来调整 Keras 神经网络超参数。

#### 方法:

1.  我们将包装在 scikit 中使用的 Keras 模型——学习使用 KerasClassifier，它是一个包装器。
2.  我们将使用使用 KerasClassifier 和 GridSearchCV 的交叉验证
3.  调整超参数，如时期数、神经元数和批次大小。

#### 为 Keras 实现 scikit-learn 分类器应用编程接口；

> tf.keras.wrappers.scikit_learn。KerasClassifier（
> 
> build _ fn =无，**sk_params
> 
> )

**Code:**

```
# import the libraries 
import tensorflow as tf
import pandas as pd
from sklearn.compose import ColumnTransformer
from sklearn.preprocessing import OneHotEncoder
from keras.wrappers.scikit_learn import KerasClassifier
from sklearn.model_selection import GridSearchCV
from sklearn.preprocessing import LabelEncoder
from sklearn.preprocessing import StandardScaler
```

数据集可以从这里的
下载导入数据集，使用该数据集我们可以预测客户是留下还是离开。

**代码:**

```
# The last column is a binary value
dataset = pd.read_csv('Churn_Modelling.csv')
X = dataset.iloc[:, 3:-1].values
y = dataset.iloc[:, -1].values
```

**编码:数据预处理**

```
le = LabelEncoder()
X[:, 2] = le.fit_transform(X[:, 2])
#perform one hot encoding 
ct = ColumnTransformer(transformers=[('encoder', OneHotEncoder(), [1])], remainder='passthrough')
X = np.array(ct.fit_transform(X))
# perform standardization of the data. 
sc = StandardScaler()
X = sc.fit_transform(X)
```

要使用 KerasClassifier 包装器，我们需要在一个函数中构建我们的模型，该函数需要传递给 KerasClassifier 构造函数中的 *build_fn* 参数。

**代码:**

```
def build_clf(unit):
  # creating the layers of the NN
  ann = tf.keras.models.Sequential()
  ann.add(tf.keras.layers.Dense(units=unit, activation='relu'))
  ann.add(tf.keras.layers.Dense(units=unit, activation='relu'))
  ann.add(tf.keras.layers.Dense(units=1, activation='sigmoid'))
  ann.compile(optimizer = 'adam', loss = 'binary_crossentropy', metrics = ['accuracy'])
  return ann
```

**代码:创建 KerasClassifier 类的对象**

```
model=KerasClassifier(build_fn=build_clf)
```

现在我们将创建我们想要调优的参数的字典，并在 GridSearchCV 中作为参数传递。

**代码:**

```
params={'batch_size':[100, 20, 50, 25, 32], 
        'nb_epoch':[200, 100, 300, 400],
        'unit':[5,6, 10, 11, 12, 15],

        }
gs=GridSearchCV(estimator=model, param_grid=params, cv=10)
# now fit the dataset to the GridSearchCV object. 
gs = gs.fit(X, y)
```

*best_score_* 成员给出了优化过程中观察到的最佳得分， *best_params_* 描述了获得最佳结果的参数组合。

**代码:**

```
best_params=gs.best_params_
accuracy=gs.best_score_
```

#### 输出:

> #### 精度:0.80325
> 
> #### 最佳参数:{'batch_size': 20，' nb_epoch': 200，' unit': 15}