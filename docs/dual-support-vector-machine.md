# 双支持向量机

> 原文:[https://www.geeksforgeeks.org/dual-support-vector-machine/](https://www.geeksforgeeks.org/dual-support-vector-machine/)

**先决条件:** [分离 SVM 的超平面](https://www.geeksforgeeks.org/separating-hyperplanes-in-svm/)

支持向量机的拉格朗日乘子方程。该方程可由下式给出:

<center>![\underset{\vec{w},b}{min} \underset{\vec{a}\geq 0}{max} \frac{1}{2}\left \| w \right \|^{2} - \sum_{j}a_j\left [ \left ( \vec{w} \cdot \vec{x}_{j} \right )y_j - 1 \right ]](img/7944d8c6bc6d34c26d73cf2eb21550b3.png "Rendered by QuickLaTeX.com")</center>

现在，根据对偶原理，上述优化问题既可以看作是原始的(最小化超过 w 和 *b)* 也可以看作是对偶的(最大化超过 *a* )。

<center>![\underset{\vec{a}\geq 0}{max}\underset{\vec{w},b}{min} \frac{1}{2}\left \| w \right \|^{2} - \sum_{j}a_j\left [ \left ( \vec{w} \cdot \vec{x}_{j} \right )y_j - 1 \right ]](img/03f72e53bf384ed9831be48769082444.png "Rendered by QuickLaTeX.com")</center>

凸优化的斯莱特条件保证了这两个问题是等价的。

为了获得最小 wrt w 和 b，这些变量的一阶偏导数 wrt 必须为 0:

<center>![\frac{\partial L}{\partial w} = w -\sum_j a_j y_j x_j =0 \\ w = \sum_j a_j y_j x_j \\ \\ \\ Wrt \, b \\ \\ \frac{\partial L}{\partial b} = -\sum_j a_j y_j  =0 \\ \\ \sum_j a_j y_j  =0](img/ebca1b2f4fae60150c63d8ec106bd85d.png "Rendered by QuickLaTeX.com")</center>

现在，把上面的方程放在拉格朗日乘数方程中，并简化它。

<center>![L  =  \frac{1}{2}\left ( \sum_i \alpha_i y_i x_i \right )\cdot\left ( \sum_j \alpha_j y_j x_j \right ) - \left ( \sum_i \alpha_i y_i x_i \right )\cdot\left ( \sum_j \alpha_j y_j x_j \right ) - \sum_i\left ( \alpha_i y_i b \right ) + \sum_i\left ( \alpha_{i}  \right ) \\](img/da9ca5bd31991bc60df08071e30b4b2e.png "Rendered by QuickLaTeX.com")</center>

在上式中，术语

<center>![\sum_i\left ( \alpha_i y_i b \right )  = 0     ](img/306498945c32f0c4837740d642c55cea.png "Rendered by QuickLaTeX.com")</center>

 because, *b* is just a constant and the rest is from the above equation”

<center>![L = \sum \alpha_i - \frac{1}{2}\sum_i \sum_j \alpha_{i} \alpha_{j} y_i y_j \left ( x_i \cdot x_j \right ) \alpha_j \geq 0 \forall j](img/9535c2351ea9290e24a67ab20ce56bf5.png "Rendered by QuickLaTeX.com")</center>

为了找到 b，我们也可以使用上面的等式和约束

<center>![\alpha_j > 0 \,for \,some\, j           ](img/88612581c8554141743aafe7a12781cf.png "Rendered by QuickLaTeX.com")</center>

 :

<center>![y_j\left ( \vec{w}\cdot\vec{x} + b  \right ) = 1 \\ \\ y_jy_j\left ( \vec{w}\cdot\vec{x} + b  \right ) = y_j \\ \\ y_j \in \left \{ -1,1 \right \} \\ \\ \left ( \vec{w}\cdot\vec{x} + b  \right ) = y_j \\ \\ b = y_k - w \cdot x_k \forall k where \, \alpha_k > 0](img/0b4306fd38481c734767e209acb8c976.png "Rendered by QuickLaTeX.com")</center>

现在，决策规则可以由下式给出:

<center>![y_i = sign(\sum \alpha_{i} y_i \left ( \vec{x}_i \cdot \vec{x} \right ) +b  )](img/6b01d091646d5fd1c220752e9cde895d.png "Rendered by QuickLaTeX.com")</center>

注意，从上面的规则我们可以观察到，拉格朗日乘数只是依赖于 x <sub>i</sub> 与未知变量 x 的点积，这个点积定义为核函数，用 K 表示

<center>![L = \sum \alpha_i - \frac{1}{2}\sum_i \sum_j \alpha_{i} \alpha_{j} y_i y_j  K(x_i,x_j) \\ \\ where K = (x_i.x_j)](img/c3791069f0c65f80d0220a8bdbf30f1f.png "Rendered by QuickLaTeX.com")</center>

现在，对于线性不可分的情况，对偶方程变成:

<center>![\underset{\alpha}{max} \sum_i \alpha_i  -  \sum_{i,j} \alpha_i \alpha_j y_i y_j x_i \cdot x_j \\ \\ for, \\ \\ \sum_i \alpha_i y_i =0 \\ \\ 0 \leq \alpha_i \leq C](img/ad80f5879e592525db5c431e7845c372.png "Rendered by QuickLaTeX.com")</center>

这里，我们添加了一个常数 C，之所以需要它是因为以下原因:

*   它阻止

    <center>![\alpha        ](img/a3aa175868162012b3bc36b22a951c98.png "Rendered by QuickLaTeX.com")</center>

    的值来自

    <center>![\alpha \to \infty        ](img/cb0e8a035994978215ccfc04d465edac.png "Rendered by QuickLaTeX.com")</center>

    。
*   它还防止模型过度拟合，这意味着一些错误分类是可以接受的。

![](img/67fc51f5d43e1d165456461d24b48b61.png)

图像描绘变换

我们将变换应用到另一个空间，如下所示。注意，我们不需要专门计算变换函数，我们只需要找到那些得到核函数的点积，然而，这个变换函数可以很容易地建立起来。

<center>![K =  \phi(i) \cdot \phi(j)](img/a2cba557eb20b125de895a14691600cd.png "Rendered by QuickLaTeX.com")</center>

哪里，

<center>![\phi()    ](img/14c4b818bb9c3132ecb748bb2ad71b57.png "Rendered by QuickLaTeX.com")</center>

 is the transformation function.

直觉告诉我们，很多时候，一个数据可以被一个更高维度的超平面分割开来。让我们更详细地看看这个:

假设我们有一个数据集，它只包含 1 个自变量和 1 个因变量。下图显示了数据:

![](img/9b4b5b923e1ccaf677c7ee8f908685a0.png)

现在，在上面的图中，很难分离清楚地分离不同类的数据点的 1D-超平面(点)。但是当通过使用某种转换转换到 2d 时，它提供了分离类的选项。

![](img/0fa6b5d5db4ad9ee16910f28b21ba1a4.png)

在上面的例子中，我们可以看到 SVM 线可以清楚地将数据集的两个类别分开。

有一些非常常用的著名内核:

*   n 次多项式

<center>![K(u,v) = (u \cdot v)^{n}](img/c796629f7088fee2884bdcf471c974d0.png "Rendered by QuickLaTeX.com")</center>

*   n 次以下的多项式

<center>![K(u,v) = (u \cdot v + 1)^{n}](img/1de2dbd90eba0bad9f71a719aeb5fb0c.png "Rendered by QuickLaTeX.com")</center>

*   高斯/径向基函数核

<center>![K(\vec{u}, \vec{v}) = e^{-\frac{\left \| \vec{u}-\vec{v} \right \|_{2}^{2}}{2 \sigma^2}}](img/14762d5e58316974f8d64ca5adb432fc.png "Rendered by QuickLaTeX.com")</center>

### 履行

## 蟒蛇 3

```
# code
import numpy as np
import matplotlib.pyplot as plt
from sklearn import svm, datasets

# import some data
cancer = datasets.load_breast_cancer()
X = cancer.data[:,:2]
Y = cancer.target

X.shape, Y.shape

# perform svm with different kernel, here c is the regularizer
h = .02
C=100
lin_svc = svm.LinearSVC(C=C)
svc = svm.SVC(kernel='linear', C=C)
rbf_svc = svm.SVC(kernel='rbf', gamma=0.7, C=C)
poly_svc = svm.SVC(kernel='poly', degree=3, C=C)

# Fit the training dataset.
lin_svc.fit(X, Y)
svc.fit(X, Y)
rbf_svc.fit(X, Y)
poly_svc.fit(X, Y)

# plot the results
x_min, x_max = X[:, 0].min() - 1, X[:, 0].max() + 1
y_min, y_max = X[:, 1].min() - 1, X[:, 1].max() + 1
xx, yy = np.meshgrid(np.arange(x_min, x_max, h),np.arange(y_min, y_max, h))

titles = ['linear kernel',
          'LinearSVC (linear kernel)',
          'RBF kernel',
          'polynomial (degree 3) kernel']

plt.figure(figsize=(10,10))

for i, clf in enumerate((svc, lin_svc,rbf_svc, poly_svc )):
    # Plot the decision boundary using the above meshgrid we generated
    plt.subplot(2, 2, i + 1)
    Z = clf.predict(np.c_[xx.ravel(), yy.ravel()])

    # Put the result into a color plot
    Z = Z.reshape(xx.shape)
    plt.set_cmap(plt.cm.flag_r)
    plt.contourf(xx, yy, Z)

    # Plot also the training points
    plt.scatter(X[:, 0], X[:, 1], c=Y)

    plt.title(titles[i])

plt.show()
```

```
((569, 2), (569,))
```

![](img/416d95014be92217318dd9ab2f1b6566.png)

SVM 使用不同的内核。

### **参考文献:**

*   [**麻省理工开放式课程幻灯片 SVM**](http://people.csail.mit.edu/dsontag/courses/ml13/slides/lecture6.pdf)