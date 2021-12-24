# Python 中的集成方法

> 原文:[https://www.geeksforgeeks.org/ensemble-methods-in-python/](https://www.geeksforgeeks.org/ensemble-methods-in-python/)

整体是指作为一个整体而不是单独看待的一组元素。集成方法创建多个模型，并将它们组合起来进行求解。集成方法有助于提高模型的鲁棒性/可推广性。在本文中，我们将讨论一些方法及其在 Python 中的实现。为此，我们从 UCI 存储库中选择一个 [**数据集**](https://archive.ics.uci.edu/ml/datasets/Alcohol+QCM+Sensor+Dataset) 。

### 基本集成方法

**1。平均法:**主要用于回归问题。该方法包括独立建立多个模型，并返回所有模型的预测平均值。一般来说，组合输出比单个输出好，因为方差减少了。

在下面的示例中，训练了三个回归模型(线性回归、xgboost 和随机森林)，并对它们的预测进行了平均。最终的预测输出是 pred_final。

## 蟒蛇 3

```py
# importing utility modules
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error

# importing machine learning models for prediction
from sklearn.ensemble import RandomForestRegressor
import xgboost as xgb
from sklearn.linear_model import LinearRegression

# loading train data set in dataframe from train_data.csv file
df = pd.read_csv("train_data.csv")

# getting target data from the dataframe
target = df["target"]

# getting train data from the dataframe
train = df.drop("target")

# Splitting between train data into training and validation dataset
X_train, X_test, y_train, y_test = train_test_split(
    train, target, test_size=0.20)

# initializing all the model objects with default parameters
model_1 = LinearRegression()
model_2 = xgb.XGBRegressor()
model_3 = RandomForestRegressor()

# training all the model on the training dataset
model_1.fit(X_train, y_target)
model_2.fit(X_train, y_target)
model_3.fit(X_train, y_target)

# predicting the output on the validation dataset
pred_1 = model_1.predict(X_test)
pred_2 = model_2.predict(X_test)
pred_3 = model_3.predict(X_test)

# final prediction after averaging on the prediction of all 3 models
pred_final = (pred_1+pred_2+pred_3)/3.0

# printing the root mean squared error between real value and predicted value
print(mean_squared_error(y_test, pred_final))
```

**输出:**

```py
4560
```

**2。最大投票:**主要用于分类问题。该方法包括独立构建多个模型，并获得各自的输出，称为“投票”。投票数最多的类作为输出返回。

在下面的例子中，三个分类模型(逻辑回归、xgboost 和随机森林)使用 [sklearn VotingClassifier](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.VotingClassifier.html) 进行组合，该模型被训练并且具有最大投票的类被返回作为输出。最终的预测输出是 pred_final。请注意，这是一种分类，而不是回归，因此损失可能不同于其他类型的集成方法。

## 蟒蛇

```py
# importing utility modules
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.metrics import log_loss

# importing machine learning models for prediction
from sklearn.ensemble import RandomForestClassifier
from xgboost import XGBClassifier
from sklearn.linear_model import LogisticRegression

# importing voting classifier
from sklearn.ensemble import VotingClassifier

# loading train data set in dataframe from train_data.csv file
df = pd.read_csv("train_data.csv")

# getting target data from the dataframe
target = df["Weekday"]

# getting train data from the dataframe
train = df.drop("Weekday")

# Splitting between train data into training and validation dataset
X_train, X_test, y_train, y_test = train_test_split(
    train, target, test_size=0.20)

# initializing all the model objects with default parameters
model_1 = LogisticRegression()
model_2 = XGBClassifier()
model_3 = RandomForestClassifier()

# Making the final model using voting classifier
final_model = VotingClassifier(
    estimators=[('lr', model_1), ('xgb', model_2), ('rf', model_3)], voting='hard')

# training all the model on the train dataset
final_model.fit(X_train, y_train)

# predicting the output on the test dataset
pred_final = final_model.predict(X_test)

# printing log loss between actual and predicted value
print(log_loss(y_test, pred_final))
```

**输出:**

```py
231
```

让我们来看看更高级的集成方法

### 高级集成方法

集成方法广泛应用于经典的机器学习中。使用 bagging 的算法的例子是随机森林和 bagging 元估计器，使用 boosting 的算法的例子是 GBM、XGBM、Adaboost 等。

作为机器学习模型的开发者，强烈建议使用集成方法。集合方法被广泛应用于几乎所有的竞赛和研究论文中。

**1。堆叠:**是通过元模型(元分类器或元回归)组合多个模型(分类或回归)的集成方法。基础模型在完整的数据集上训练，然后元模型在从基础模型返回的特征(作为输出)上训练。堆叠中的基本模型通常是不同的。元模型有助于从基本模型中找到特征，以获得最佳的准确性。

**算法:**

> 1.  将训练数据集分成 n 个部分
> 2.  将基本模型(如线性回归)拟合到 n-1 个部分，并预测第 n 个部分。这是针对列车组的 N 个部分中的每个部分完成的。
> 3.  然后在整个列车数据集上拟合基本模型。
> 4.  该模型用于预测测试数据集。
> 5.  对另一个基本模型重复步骤 2 至 4，这将为训练和测试数据集生成另一组预测。
> 6.  使用列车数据集上的预测作为构建新模型的特征。
> 7.  最终模型用于测试数据集

上进行预测

堆叠有点不同于基本的集合方法，因为它有一级和二级模型。首先通过用所有一级模型训练数据集来提取堆叠特征。然后，第一级模型使用列车堆叠特征来训练模型，然后该模型使用测试堆叠特征来预测最终输出。

## 蟒 3

```py
# importing utility modules
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error

# importing machine learning models for prediction
from sklearn.ensemble import RandomForestRegressor
import xgboost as xgb
from sklearn.linear_model import LinearRegression

# importing stacking lib
from vecstack import stacking

# loading train data set in dataframe from train_data.csv file
df = pd.read_csv("train_data.csv")

# getting target data from the dataframe
target = df["target"]

# getting train data from the dataframe
train = df.drop("target")

# Splitting between train data into training and validation dataset
X_train, X_test, y_train, y_test = train_test_split(
    train, target, test_size=0.20)

# initializing all the base model objects with default parameters
model_1 = LinearRegression()
model_2 = xgb.XGBRegressor()
model_3 = RandomForestRegressor()

# putting all base model objects in one list
all_models = [model_1, model_2, model_3]

# computing the stack features
s_train, s_test = stacking(all_models, X_train, X_test,
                           y_train, regression=True, n_folds=4)

# initializing the second-level model
final_model = model_1

# fitting the second level model with stack features
final_model = final_model.fit(s_train, y_train)

# predicting the final output using stacking
pred_final = final_model.predict(X_test)

# printing the root mean squared error between real value and predicted value
print(mean_squared_error(y_test, pred_final))
```

**输出:**

```py
4510 
```

**2。混合:**它类似于上面解释的堆叠方法，但是不是使用整个数据集来训练基础模型，而是将验证数据集分开来进行预测。

**算法:**

> 1.  将训练数据集拆分为训练、测试和验证数据集。
> 2.  用训练数据集拟合所有基本模型。
> 3.  预测验证和测试数据集。
> 4.  这些预测被用作构建二级模型的特征
> 5.  该模型用于测试和元功能

## 进行预测

```py
# importing utility modules
import pandas as pd
from sklearn.metrics import mean_squared_error

# importing machine learning models for prediction
from sklearn.ensemble import RandomForestRegressor
import xgboost as xgb
from sklearn.linear_model import LinearRegression

# importing train test split
from sklearn.model_selection import train_test_split

# loading train data set in dataframe from train_data.csv file
df = pd.read_csv("train_data.csv")

# getting target data from the dataframe
target = df["target"]

# getting train data from the dataframe
train = df.drop("target")

#Splitting between train data into training and validation dataset
X_train, X_test, y_train, y_test = train_test_split(train, target, test_size=0.20)

# performing the train test and validation split
train_ratio = 0.70
validation_ratio = 0.20
test_ratio = 0.10

# performing train test split
x_train, x_test, y_train, y_test = train_test_split(
    train, target, test_size=1 - train_ratio)

# performing test validation split
x_val, x_test, y_val, y_test = train_test_split(
    x_test, y_test, test_size=test_ratio/(test_ratio + validation_ratio))

# initializing all the base model objects with default parameters
model_1 = LinearRegression()
model_2 = xgb.XGBRegressor()
model_3 = RandomForestRegressor()

# training all the model on the train dataset

# training first model
model_1.fit(x_train, y_train)
val_pred_1 = model_1.predict(x_val)
test_pred_1 = model_1.predict(x_test)

# converting to dataframe
val_pred_1 = pd.DataFrame(val_pred_1)
test_pred_1 = pd.DataFrame(test_pred_1)

# training second model
model_2.fit(x_train, y_train)
val_pred_2 = model_2.predict(x_val)
test_pred_2 = model_2.predict(x_test)

# converting to dataframe
val_pred_2 = pd.DataFrame(val_pred_2)
test_pred_2 = pd.DataFrame(test_pred_2)

# training third model
model_3.fit(x_train, y_train)
val_pred_3 = model_1.predict(x_val)
test_pred_3 = model_1.predict(x_test)

# converting to dataframe
val_pred_3 = pd.DataFrame(val_pred_3)
test_pred_3 = pd.DataFrame(test_pred_3)

# concatenating validation dataset along with all the predicted validation data (meta features)
df_val = pd.concat([x_val, val_pred_1, val_pred_2, val_pred_3], axis=1)
df_test = pd.concat([x_test, test_pred_1, test_pred_2, test_pred_3], axis=1)

# making the final model using the meta features
final_model = LinearRegression()
final_model.fit(df_val, y_val)

# getting the final output
final_pred = final_model.predict(df_test)

#printing the root mean squared error between real value and predicted value
print(mean_squared_error(y_test, pred_final))
```

**输出:**

```py
4790 
```

**3。装袋:**也叫自举法。基础模型在包上运行，以获得整个数据集的公平分布。包是数据集的一个子集，还有一个替换包，用于使包的大小与整个数据集相同。最终输出是在组合所有基础模型的输出后形成的。

**算法:**

> 1.  通过替换选择观察值，从训练数据集中创建多个数据集
> 2.  对每个创建的数据集独立运行一个基本模型
> 3.  将所有基本模型的预测合并到每个最终输出中

打包通常只使用一个基本模型(在下面的代码中使用了 XGBoost 回归器)。

## 巨蟒

```py
# importing utility modules
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error

# importing machine learning models for prediction
import xgboost as xgb

# importing bagging module
from sklearn.ensemble import BaggingRegressor

# loading train data set in dataframe from train_data.csv file
df = pd.read_csv("train_data.csv")

# getting target data from the dataframe
target = df["target"]

# getting train data from the dataframe
train = df.drop("target")

# Splitting between train data into training and validation dataset
X_train, X_test, y_train, y_test = train_test_split(
    train, target, test_size=0.20)

# initializing the bagging model using XGboost as base model with default parameters
model = BaggingRegressor(base_estimator=xgb.XGBRegressor())

# training model
model.fit(X_train, y_train)

# predicting the output on the test dataset
pred = model.predict(X_test)

# printing the root mean squared error between real value and predicted value
print(mean_squared_error(y_test, pred_final))
```

**输出:**

```py
4666 
```

**4。Boosting:** Boosting 是一种顺序方法——它旨在防止错误的基础模型影响最终输出。该方法不是对基本模型进行组合，而是专注于构建一个依赖于前一个模型的新模型。一个新的模型试图消除前一个模型的错误。这些模型中的每一个都被称为弱学习者。最终模型(又称强学习者)是通过获取所有弱学习者的加权平均值而形成的。

**算法:**

> 1.  取训练数据集的一个子集。
> 2.  在这个数据集上训练基本模型。
> 3.  使用第三个模型来预测整个数据集。
> 4.  利用预测值和实际值计算误差。
> 5.  用相同的权重初始化所有数据点。
> 6.  对错误预测的数据点给予更高的权重。
> 7.  制作另一个模型，用新模型进行预测，从而减少/纠正前一个模型所犯的错误。
> 8.  同样，创建多个模型-每个连续的模型都会纠正前一个模型的错误。
> 9.  最终模型(强学习者)是所有先前模型(弱学习者)的加权平均值。

## 蟒 3

```py
# importing utility modules
import pandas as pd
from sklearn.model_selection import train_test_split
from sklearn.metrics import mean_squared_error

# importing machine learning models for prediction
from sklearn.ensemble import GradientBoostingRegressor

# loading train data set in dataframe from train_data.csv file
df = pd.read_csv("train_data.csv")

# getting target data from the dataframe
target = df["target"]

# getting train data from the dataframe
train = df.drop("target")

# Splitting between train data into training and validation dataset
X_train, X_test, y_train, y_test = train_test_split(
    train, target, test_size=0.20)

# initializing the boosting module with default parameters
model = GradientBoostingRegressor()

# training the model on the train dataset
model.fit(X_train, y_train)

# predicting the output on the test dataset
pred_final = model.predict(X_test)

# printing the root mean squared error between real value and predicted value
print(mean_squared_error(y_test, pred_final))
```

**输出:**

```py
4789 
```

**注意:****[scikit-learn](https://scikit-learn.org/stable/modules/ensemble.html)为集成方法提供了几个模块/方法。请注意，一种方法的准确性并不意味着一种方法优于另一种方法。本文旨在简要介绍集成方法，而不是对它们进行比较。程序员必须使用适合数据的方法。**