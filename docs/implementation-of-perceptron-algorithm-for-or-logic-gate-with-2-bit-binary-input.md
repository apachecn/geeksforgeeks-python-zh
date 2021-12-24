# 2 位二进制输入或逻辑门感知器算法的实现

> 原文:[https://www . geeksforgeeks . org/2 位二进制输入或逻辑门的感知器算法实现/](https://www.geeksforgeeks.org/implementation-of-perceptron-algorithm-for-or-logic-gate-with-2-bit-binary-input/)

在机器学习领域，感知器是一种用于二进制分类器的监督学习算法。感知器模型实现以下功能:

![\[ \begin{array}{c} \hat{y}=\Theta\left(w_{1} x_{1}+w_{2} x_{2}+\ldots+w_{n} x_{n}+b\right) \\ =\Theta(\mathbf{w} \cdot \mathbf{x}+b) \\ \text { where } \Theta(v)=\left\{\begin{array}{cc} 1 & \text { if } v \geqslant 0 \\ 0 & \text { otherwise } \end{array}\right. \end{array} \]](img/7a525c5fa0f2cf3118ef7158b4d5b176.png "Rendered by QuickLaTeX.com")

对于权重向量![$\boldsymbol{w}$](img/b85c5d684ed173b293bb6e1c77dbb63c.png "Rendered by QuickLaTeX.com")和偏差参数![$\boldsymbol{b}$](img/c7ccd739aed60032fc89fa01d6512f60.png "Rendered by QuickLaTeX.com")的特定选择，模型预测相应输入向量![$\boldsymbol{x}$](img/8a021e6b8f75d1f8dd7535d27ea03254.png "Rendered by QuickLaTeX.com")的输出![$\boldsymbol{\hat{y}}$](img/a6e8955385eea2eb103e7a07d209a00c.png "Rendered by QuickLaTeX.com")。

**或*****2 位二进制变量*** 的逻辑函数真值表，即输入向量![$\boldsymbol{x} : (\boldsymbol{x_{1}}, \boldsymbol{x_{2}})$](img/78d53309f09fecf584615fd711306497.png "Rendered by QuickLaTeX.com")和相应的输出![$\boldsymbol{y}$](img/2a77d93c3050965e762fdc689edaab6e.png "Rendered by QuickLaTeX.com")–

| ![$\boldsymbol{x_{1}}$](img/4a0a3c212c46d96f633f15b9a7b33864.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{x_{2}}$](img/68ff94b5056f37ca7234d1bff5e655bf.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{y}$](img/2a77d93c3050965e762fdc689edaab6e.png "Rendered by QuickLaTeX.com") |
| --- | --- | --- |
| Zero | Zero | Zero |
| Zero | one | one |
| one | Zero | one |
| one | one | one |

现在对于输入向量![$\boldsymbol{x} : (\boldsymbol{x_{1}}, \boldsymbol{x_{2}})$](img/78d53309f09fecf584615fd711306497.png "Rendered by QuickLaTeX.com")的相应权重向量![$\boldsymbol{w} : (\boldsymbol{w_{1}}, \boldsymbol{w_{2}})$](img/094e9945bcbef60421988602f7f77a3c.png "Rendered by QuickLaTeX.com")，关联的感知器函数可以定义为:

![\[$\boldsymbol{\hat{y}} = \Theta\left(w_{1} x_{1}+w_{2} x_{2}+b\right)$\]](img/f067d788d627f83e4bce96cbd2064083.png "Rendered by QuickLaTeX.com")

![](img/ec017a37c6fea7f70a01bbd5b796101f.png)
为实现，考虑的权重参数为![$\boldsymbol{w_{1}} = 1, \boldsymbol{w_{2}} = 1$](img/4f0b835d5bdfee2fa936f4ad528af080.png "Rendered by QuickLaTeX.com")，偏差参数为![$\boldsymbol{b} = -0.5$](img/094e5220d4f09cf7e39702bcfe1a2939.png "Rendered by QuickLaTeX.com")。

**Python 实现:**

```py
# importing Python library
import numpy as np

# define Unit Step Function
def unitStep(v):
    if v >= 0:
        return 1
    else:
        return 0

# design Perceptron Model
def perceptronModel(x, w, b):
    v = np.dot(w, x) + b
    y = unitStep(v)
    return y

# OR Logic Function
# w1 = 1, w2 = 1, b = -0.5
def OR_logicFunction(x):
    w = np.array([1, 1])
    b = -0.5
    return perceptronModel(x, w, b)

# testing the Perceptron Model
test1 = np.array([0, 1])
test2 = np.array([1, 1])
test3 = np.array([0, 0])
test4 = np.array([1, 0])

print("OR({}, {}) = {}".format(0, 1, OR_logicFunction(test1)))
print("OR({}, {}) = {}".format(1, 1, OR_logicFunction(test2)))
print("OR({}, {}) = {}".format(0, 0, OR_logicFunction(test3)))
print("OR({}, {}) = {}".format(1, 0, OR_logicFunction(test4)))
```

**Output:**

```py
OR(0, 1) = 1
OR(1, 1) = 1
OR(0, 0) = 0
OR(1, 0) = 1

```

这里，根据 2 位二进制输入的真值表，每个测试输入的模型预测输出(![$\boldsymbol{\hat{y}}$](img/a6e8955385eea2eb103e7a07d209a00c.png "Rendered by QuickLaTeX.com"))与或逻辑门常规输出(![$\boldsymbol{y}$](img/2a77d93c3050965e762fdc689edaab6e.png "Rendered by QuickLaTeX.com"))精确匹配。
由此验证了或逻辑门的感知器算法是正确实现的。