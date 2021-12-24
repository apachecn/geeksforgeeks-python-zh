# 多任务套索回归

> 原文:[https://www.geeksforgeeks.org/multi-task-lasso-regression/](https://www.geeksforgeeks.org/multi-task-lasso-regression/)

**多任务套索** **回归**是套索回归的增强版。MultiTaskLasso 是 sklearn 提供的模型，用于多元回归问题，通过估计它们的稀疏系数来协同工作。所有称为任务的回归问题都有相同的特征。该模型使用混合 l1/l2 范数进行正则化训练。它在许多方面类似于套索回归。主要区别在于α参数，其中α是乘以 l1/l2 范数的常数。

多任务套索模型有以下参数:

> **α:**乘以 l1/l2 范数的浮点值。默认 1.0
> **fit_intercept:** 决定是否使用 intercept 进行计算。
> **归一化:**用于归一化数据中的回归子
> **max_itr:** 最大迭代次数。默认情况下-1000
> **选择:**确定系数的上升将如何发生——值{ '循环'，'随机' }默认情况下循环
> **公差:**进行优化。
> **随机 _ 状态:**选择一个随机特征进行更新。

**代码:用 python 说明 MultiTaskLasso 回归的工作方式**

## 蟒蛇 3

```py
# import linear model library
from sklearn import linear_model

# create MultiTaskLasso model
MTL = linear_model.MultiTaskLasso(alpha = 0.5)

# fit the model to a data
MTL.fit([[1, 0], [1, 3], [2, 2]], [[0, 2], [1, 4], [2, 4]])

# perform prediction and print the result
print("Prediction result: \n", MTL.predict([[0, 1]]), "\n")

# print the coefficients
print("Coefficients: \n", MTL.coef_, "\n")

# print the intercepts
print("Intercepts: \n", MTL.intercept_, "\n")

# print the number of iterations performed
print("Number of Iterations: ", MTL.n_iter_, "\n")
```

**输出:**

```py
Prediction result: 
[[0.8245348  3.04089134]] 

Coefficients: 
[[0\.         0.26319779]
 [0\.         0.43866299]] 

Intercepts:
[0.56133701 2.60222835] 

Number of Iterations: 2
```