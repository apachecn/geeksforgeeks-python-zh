# 使用统计模型的逻辑回归

> 原文:[https://www . geeksforgeeks . org/logistic-回归-使用-statsmodels/](https://www.geeksforgeeks.org/logistic-regression-using-statsmodels/)

**先决条件:** [理解逻辑回归](https://www.geeksforgeeks.org/understanding-logistic-regression/)
逻辑回归是一种回归分析，用于发现某一事件发生的概率。对于我们有一个只能取离散值的分类因变量的情况，这是最适合的回归类型。

**数据集:**
在本文中，我们将根据学生的 gmat、gpa 成绩和工作经验来预测他们是否会被某所大学录取。这里的因变量是一个**二元逻辑变量**，预计它将严格采取两种形式之一，即*允许*或*不允许*。

## 建立逻辑回归模型:

**Statsmodels** 是一个 Python 模块，提供各种功能来估计不同的统计模型和执行统计测试

*   首先，我们定义依赖( **y** )和独立( **X** )变量的集合。如果因变量为非数字形式，则首先使用假人将其转换为数字。示例中用于训练模型的文件，可以在[这里](https://drive.google.com/file/d/1g4Ib_zuG_hJG6VWlXvqANti69w5cM66K/view?usp=sharing)下载。
*   Statsmodels 提供了用于执行逻辑回归的 **Logit()** 函数。 *Logit()* 函数接受 **y** 和 **X** 作为参数，返回 *Logit* 对象。然后将模型与数据进行拟合。

## 蟒蛇 3

```
# importing libraries
import statsmodels.api as sm
import pandas as pd

# loading the training dataset
df = pd.read_csv('logit_train1.csv', index_col = 0)

# defining the dependent and independent variables
Xtrain = df[['gmat', 'gpa', 'work_experience']]
ytrain = df[['admitted']]

# building the model and fitting the data
log_reg = sm.Logit(ytrain, Xtrain).fit()
```

**输出:**

```
Optimization terminated successfully.
         Current function value: 0.352707
         Iterations 8
```

在输出中，*迭代*指模型迭代数据的次数，试图优化模型。默认情况下，执行的最大迭代次数为 35 次，此后优化将失败。

## 汇总表:

下表给出了回归结果的描述性总结。

## 蟒蛇 3

```
# printing the summary table
print(log_reg.summary())
```

**输出:**

```
                           Logit Regression Results                           
==============================================================================
Dep. Variable:               admitted   No. Observations:                   30
Model:                          Logit   Df Residuals:                       27
Method:                           MLE   Df Model:                            2
Date:                Wed, 15 Jul 2020   Pseudo R-squ.:                  0.4912
Time:                        16:09:17   Log-Likelihood:                -10.581
converged:                       True   LL-Null:                       -20.794
Covariance Type:            nonrobust   LLR p-value:                 3.668e-05
===================================================================================
                      coef    std err          z      P>|z|      [0.025      0.975]
-----------------------------------------------------------------------------------
gmat               -0.0262      0.011     -2.383      0.017      -0.048      -0.005
gpa                 3.9422      1.964      2.007      0.045       0.092       7.792
work_experience     1.1983      0.482      2.487      0.013       0.254       2.143
===================================================================================
```

汇总表中一些术语的解释:

*   **coef :** 回归方程中自变量的系数。
*   **对数似然:**最大似然估计(MLE)函数的自然对数。最大似然估计是寻找最佳拟合的参数集的优化过程。
*   **LL-Null :** 不含自变量(只含截距)时模型的对数似然值。
*   **伪 R-squ。:**最小二乘线性回归中 [R 平方](https://www.geeksforgeeks.org/ml-r-squared-in-regression-analysis/)值的替代品。它是零模型与全模型的对数似然比。

## 根据新数据进行预测:

现在我们将在新的测试数据上测试我们的模型。测试数据从[这个](https://drive.google.com/file/d/1fPJrN3i7ZxP_c7WjSbxskIoiAnSLDn36/view?usp=sharing) csv 文件加载。
**预测()**功能可用于执行预测。得到的预测是分数(0 到 1 之间)，表示被录取的概率。因此，这些值被舍入，以获得 1 或 0 的离散值。

## 蟒蛇 3

```
# loading the testing dataset 
df = pd.read_csv('logit_test1.csv', index_col = 0)

# defining the dependent and independent variables
Xtest = df[['gmat', 'gpa', 'work_experience']]
ytest = df['admitted']

# performing predictions on the test datdaset
yhat = log_reg.predict(Xtest)
prediction = list(map(round, yhat))

# comparing original and predicted values of y
print('Actual values', list(ytest.values))
print('Predictions :', prediction)
```

**输出:**

```
Optimization terminated successfully.
         Current function value: 0.352707
         Iterations 8
Actual values [0, 0, 0, 0, 0, 1, 1, 0, 1, 1]
Predictions : [0, 0, 0, 0, 0, 0, 0, 0, 1, 1]
```

测试模型的准确性:

## 蟒蛇 3

```
from sklearn.metrics import (confusion_matrix,
                           accuracy_score)

# confusion matrix
cm = confusion_matrix(ytest, prediction)
print ("Confusion Matrix : \n", cm)

# accuracy score of the model
print('Test accuracy = ', accuracy_score(ytest, prediction))
```

**输出:**

```
Confusion Matrix : 
 [[6 0]
 [2 2]]
Test accuracy =  0.8
```