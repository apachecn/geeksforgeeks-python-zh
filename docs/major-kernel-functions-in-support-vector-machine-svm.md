# 支持向量机(SVM)中的主要核函数

> 原文:[https://www . geeksforgeeks . org/main-kernel-functions-in-support-vector-machine/](https://www.geeksforgeeks.org/major-kernel-functions-in-support-vector-machine-svm/)

**核函数**是一种以数据为输入，转换成处理数据所需形式的方法。使用“核”是因为支持向量机中使用的一组数学函数提供了操作数据的窗口。因此，核函数通常对训练数据集进行变换，使得非线性决策表面能够在更高维空间中变换成线性方程。基本上，它返回标准特征尺寸中两点之间的内积。

**标准核函数方程:**

<center>![K (\bar{x}) = 1, if ||\bar{x}|| <= 1](img/3d0035c7ea09ebf536ed88be5484fbf6.png "Rendered by QuickLaTeX.com")
![K (\bar{x}) = 0, Otherwise](img/83175cb3a0f9882b09fe10784b4e027c.png "Rendered by QuickLaTeX.com")</center>

**主要内核函数:-**

为了实现内核函数，首先我们必须使用命令提示终端安装“scikit-learn”库:

```py
    pip install scikit-learn

```

*   **高斯核:**用于在没有数据先验知识的情况下进行变换。

<center>![K (x, y) = e ^ - (\frac{||x - y||^2} {2 \sigma^2})](img/ba4a82619b85ebc7049f376c620144a3.png "Rendered by QuickLaTeX.com")</center>

*   **高斯核径向基函数(RBF) :** 同上核函数，加入径向基方法改进变换。

<center>![K (x, y) = e ^ - (\gamma{||x - y||^2})](img/ed9239ec750487196d0b43df48cc2f3c.png "Rendered by QuickLaTeX.com")
![K (x, x1) + K (x, x2) (Simplified - Formula)](img/e059f509221d146244bde4d94d621754.png "Rendered by QuickLaTeX.com")
![K (x, x1) + K (x, x2) > 0 (Green)](img/c48d11591d0942b0f42a97baa69711fc.png "Rendered by QuickLaTeX.com")
![K (x, x1) + K (x, x2) = 0 (Red) ](img/ff40fa7a0b4a81aed0cb0c81309e139c.png "Rendered by QuickLaTeX.com")</center>

<center>![](img/1d9f7dd09fcd0112329df12ad8e23f4c.png)</center>

**Code:**

```py
from sklearn.svm import SVC
classifier = SVC(kernel ='rbf', random_state = 0)
 # training set in x, y axis
classifier.fit(x_train, y_train)
```

*   **Sigmoid Kernel:** 这个函数相当于神经网络的两层、感知器模型，作为人工神经元的激活函数。

<center>![K (x, y) = tanh (\gamma.{x^T y}+{r})](img/179182ae6cb510aae6773997d51d1b38.png "Rendered by QuickLaTeX.com")
![](img/8d68a2aebf33118b8661ccfdd6a9a383.png)</center>

**代码:**

```py
from sklearn.svm import SVC
classifier = SVC(kernel ='sigmoid')
classifier.fit(x_train, y_train) # training set in x, y axis
```

*   **多项式核:**表示特征空间中训练数据集的向量与核中使用的原始变量的多项式的相似性。

<center>![K (x, y) = tanh (\gamma.{x^T y}+{r})^d, \gamma>0](img/150ce0de6f7c82aa86995a66c3a0a0c5.png "Rendered by QuickLaTeX.com")
![](img/2fb30b85ed908cf9a838c8259229e49c.png)</center>

**Code:**

```py
from sklearn.svm import SVC
classifier = SVC(kernel ='poly', degree = 4)
classifier.fit(x_train, y_train) # training set in x, y axis
```

*   [**线性核:**](https://www.geeksforgeeks.org/creating-linear-kernel-svm-in-python/) 在数据线性可分时使用。

**代码:**

```py
from sklearn.svm import SVC
classifier = SVC(kernel ='linear')
classifier.fit(x_train, y_train) # training set in x, y axis
```