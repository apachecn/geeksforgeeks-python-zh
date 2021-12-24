# 2 位二进制输入与非门感知器算法的实现

> 原文:[https://www . geeksforgeeks . org/2 位二进制输入与非门感知器算法的实现/](https://www.geeksforgeeks.org/implementation-of-perceptron-algorithm-for-nand-logic-gate-with-2-bit-binary-input/)

在机器学习领域，感知器是一种用于二进制分类器的监督学习算法。感知器模型实现以下功能:

![\[ \begin{array}{c} \hat{y}=\Theta\left(w_{1} x_{1}+w_{2} x_{2}+\ldots+w_{n} x_{n}+b\right) \\ =\Theta(\mathbf{w} \cdot \mathbf{x}+b) \\ \text { where } \Theta(v)=\left\{\begin{array}{cc} 1 & \text { if } v \geqslant 0 \\ 0 & \text { otherwise } \end{array}\right. \end{array} \]](img/7a525c5fa0f2cf3118ef7158b4d5b176.png "Rendered by QuickLaTeX.com")

对于权重向量![$\boldsymbol{w}$](img/b85c5d684ed173b293bb6e1c77dbb63c.png "Rendered by QuickLaTeX.com")和偏差参数![$\boldsymbol{b}$](img/c7ccd739aed60032fc89fa01d6512f60.png "Rendered by QuickLaTeX.com")的特定选择，模型预测相应输入向量![$\boldsymbol{x}$](img/8a021e6b8f75d1f8dd7535d27ea03254.png "Rendered by QuickLaTeX.com")的输出![$\boldsymbol{\hat{y}}$](img/a6e8955385eea2eb103e7a07d209a00c.png "Rendered by QuickLaTeX.com")。

**与非**逻辑函数真值表，用于 ***2 位二进制变量*** ，即输入向量![$\boldsymbol{x} : (\boldsymbol{x_{1}}, \boldsymbol{x_{2}})$](img/78d53309f09fecf584615fd711306497.png "Rendered by QuickLaTeX.com")和相应的输出![$\boldsymbol{y}$](img/2a77d93c3050965e762fdc689edaab6e.png "Rendered by QuickLaTeX.com")–

| ![$\boldsymbol{x_{1}}$](img/4a0a3c212c46d96f633f15b9a7b33864.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{x_{2}}$](img/68ff94b5056f37ca7234d1bff5e655bf.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{y}$](img/2a77d93c3050965e762fdc689edaab6e.png "Rendered by QuickLaTeX.com") |
| --- | --- | --- |
| Zero | Zero | one |
| Zero | one | one |
| one | Zero | one |
| one | one | Zero |

我们可以观察到，![$NAND(\boldsymbol{x_{1}}, \boldsymbol{x_{2}}) = NOT(AND(\boldsymbol{x_{1}}, \boldsymbol{x_{2}}))$](img/35432c65282dbb1cce8e1738fb75ed9d.png "Rendered by QuickLaTeX.com")
现在对于输入向量![$\boldsymbol{x} : (\boldsymbol{x_{1}}, \boldsymbol{x_{2}})$](img/78d53309f09fecf584615fd711306497.png "Rendered by QuickLaTeX.com")到 AND 节点的对应权重向量![$\boldsymbol{w} : (\boldsymbol{w_{1}}, \boldsymbol{w_{2}})$](img/094e9945bcbef60421988602f7f77a3c.png "Rendered by QuickLaTeX.com")，关联的感知器函数可以定义为:

![\[$\boldsymbol{\hat{y}\prime} = \Theta\left(w_{1} x_{1}+w_{2} x_{2}+b_{AND}\right)$ \]](img/af7fc593787b5dac9749013093a6cc5a.png "Rendered by QuickLaTeX.com")

稍后，“与”节点![$\boldsymbol{\hat{y}\prime}$](img/663d596ca30b2d64669858e69f4619ec.png "Rendered by QuickLaTeX.com")的输出是权重为![$\boldsymbol{w_{NOT}}$](img/4e10403d8f76f7b9024a360a4ecb58fa.png "Rendered by QuickLaTeX.com")的“非”节点的输入。那么相应的输出![$\boldsymbol{\hat{y}}$](img/a6e8955385eea2eb103e7a07d209a00c.png "Rendered by QuickLaTeX.com")就是与非门逻辑函数的最终输出，相关的感知器函数可以定义为:

![\[$\boldsymbol{\hat{y}} = \Theta\left(w_{NOT}  \boldsymbol{\hat{y}\prime}+b_{NOT}\right)$\]](img/e45e0c382856a6cc1b3c3f47d5337dfb.png "Rendered by QuickLaTeX.com")

![](img/632f6b0e2e39147d1217a5ca5dd614fe.png)
实施时，考虑的权重参数为![$\boldsymbol{w_{1}} = 1, \boldsymbol{w_{2}} = 1, \boldsymbol{w_{NOT}} = -1$](img/f57cf3f09f7b5af1668c357e0235ed4f.png "Rendered by QuickLaTeX.com")，偏差参数为![$\boldsymbol{b_{AND}} = -1.5, \boldsymbol{b_{NOT}} = 0.5$](img/5b2087621bb723502a08525df4f90b41.png "Rendered by QuickLaTeX.com")。

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

# NOT Logic Function
# wNOT = -1, bNOT = 0.5
def NOT_logicFunction(x):
    wNOT = -1
    bNOT = 0.5
    return perceptronModel(x, wNOT, bNOT)

# AND Logic Function
# w1 = 1, w2 = 1, bAND = -1.5
def AND_logicFunction(x):
    w = np.array([1, 1])
    bAND = -1.5
    return perceptronModel(x, w, bAND)

# NAND Logic Function
# with AND and NOT  
# function calls in sequence
def NAND_logicFunction(x):
    output_AND = AND_logicFunction(x)
    output_NOT = NOT_logicFunction(output_AND)
    return output_NOT

# testing the Perceptron Model
test1 = np.array([0, 1])
test2 = np.array([1, 1])
test3 = np.array([0, 0])
test4 = np.array([1, 0])

print("NAND({}, {}) = {}".format(0, 1, NAND_logicFunction(test1)))
print("NAND({}, {}) = {}".format(1, 1, NAND_logicFunction(test2)))
print("NAND({}, {}) = {}".format(0, 0, NAND_logicFunction(test3)))
print("NAND({}, {}) = {}".format(1, 0, NAND_logicFunction(test4)))
```

**Output:**

```py
NAND(0, 1) = 1
NAND(1, 1) = 0
NAND(0, 0) = 1
NAND(1, 0) = 1

```

这里，根据 2 位二进制输入的真值表，每个测试输入的模型预测输出(![$\boldsymbol{\hat{y}}$](img/a6e8955385eea2eb103e7a07d209a00c.png "Rendered by QuickLaTeX.com"))与与非门逻辑门常规输出(![$\boldsymbol{y}$](img/2a77d93c3050965e762fdc689edaab6e.png "Rendered by QuickLaTeX.com"))精确匹配。
因此，验证了与非门的感知器算法是正确实现的。