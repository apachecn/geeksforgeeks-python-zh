# 3 位二进制输入逻辑门的感知器算法

> 原文:[https://www . geeksforgeeks . org/感知器-3 位二进制输入逻辑门算法/](https://www.geeksforgeeks.org/perceptron-algorithm-for-logic-gate-with-3-bit-binary-input/)

在机器学习领域，感知器是一种用于二进制分类器的监督学习算法。感知器模型实现以下功能:

![\[\begin{array}{c}\hat{y}=\Theta\left(w_{1} x_{1}+w_{2} x_{2}+\ldots+w_{n} x_{n}+b\right) \\ =\Theta(\mathbf{w} \cdot \mathbf{x}+b) \\  \text { where } \Theta(v)=\left\{\begin{array}{cc} 1 & \text { if } v \geqslant 0 \\ 0 & \text { otherwise } \end{array}\right. \end{array}\]](img/e1ad3d8b1c7d22a1ab7a34d6f104a5cd.png "Rendered by QuickLaTeX.com")

对于权重向量![$\boldsymbol{w}$](img/b85c5d684ed173b293bb6e1c77dbb63c.png "Rendered by QuickLaTeX.com")和偏差参数![$\boldsymbol{b}$](img/c7ccd739aed60032fc89fa01d6512f60.png "Rendered by QuickLaTeX.com")的特定选择，模型预测相应输入向量![$\boldsymbol{x}$](img/8a021e6b8f75d1f8dd7535d27ea03254.png "Rendered by QuickLaTeX.com")的输出![$\boldsymbol{\hat{y}}$](img/a6e8955385eea2eb103e7a07d209a00c.png "Rendered by QuickLaTeX.com")。
3 位二进制变量**的 **AND、OR、NAND、NOR** 门的逻辑函数真值表，即输入向量![$\boldsymbol{x} : (\boldsymbol{x_{1}}, \boldsymbol{x_{2}}, \boldsymbol{x_{3}})$](img/a831cbd8a75b830daf8c4548fb9966df.png "Rendered by QuickLaTeX.com")和相应的输出![$\boldsymbol{y_{AND}}, \boldsymbol{y_{OR}}, \boldsymbol{y_{NAND}}, \boldsymbol{y_{NOR}}$](img/f458eaa4944ea64f2518a677636c4c76.png "Rendered by QuickLaTeX.com")–**

| ![$\boldsymbol{x_{1}}$](img/4a0a3c212c46d96f633f15b9a7b33864.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{x_{2}}$](img/68ff94b5056f37ca7234d1bff5e655bf.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{x_{3}}$](img/a049b26da3564bd6dfa3a71b961f2647.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{y_{AND}}$](img/32208570d25752dff037b7f75ef4c228.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{y_{OR}}$](img/eb61a0b95398489c527d0847f90d6242.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{y_{NAND}}$](img/c6193ac78db621fb606915f63bc7b2d1.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{y_{NOR}}$](img/d2a2467cf2b9ca090d68b68492ad45fe.png "Rendered by QuickLaTeX.com") |
| --- | --- | --- | --- | --- | --- | --- |
| Zero | Zero | Zero | Zero | Zero | one | one |
| Zero | Zero | one | Zero | one | one | Zero |
| Zero | one | Zero | Zero | one | one | Zero |
| Zero | one | one | Zero | one | one | Zero |
| one | Zero | Zero | Zero | one | one | Zero |
| one | Zero | one | Zero | one | one | Zero |
| one | one | Zero | Zero | one | one | Zero |
| one | one | one | one | one | Zero | Zero |

**现在对于输入向量![$\boldsymbol{x} : (\boldsymbol{x_{1}}, \boldsymbol{x_{2}}, \boldsymbol{x_{3}})$](img/a831cbd8a75b830daf8c4548fb9966df.png "Rendered by QuickLaTeX.com")的相应权重向量![$\boldsymbol{w} : (\boldsymbol{w_{1}}, \boldsymbol{w_{2}}, \boldsymbol{w_{3}})$](img/2cea5ea20dc00c1b6e0e99f56960df0e.png "Rendered by QuickLaTeX.com")，关联的感知器函数可以定义为:**

**![\[$\boldsymbol{\hat{y}} = \Theta\left(w_{1} x_{1}+w_{2} x_{2}+w_{3} x_{3}+b\right)$\]](img/ee9114005c5984195c61d2cbd8f7901c.png "Rendered by QuickLaTeX.com")**

**![](img/975e692c85186fa1c9f74fed5b13b522.png)
为了实现，对于每个逻辑门，考虑的权重参数是![$\boldsymbol{w_{1}}, \boldsymbol{w_{2}}, \boldsymbol{w_{3}}$](img/f961c565159c37d7aa01c04937ab5065.png "Rendered by QuickLaTeX.com")，偏置参数是![$\boldsymbol{b}$](img/c7ccd739aed60032fc89fa01d6512f60.png "Rendered by QuickLaTeX.com")**

| ![$\boldsymbol{Parameters}$](img/be627a63fc7ff6198cd50b4424c1e1a0.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{AND}$](img/0da3748d5845e15b32f8f5ea79703e13.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{OR}$](img/1ea542a3f74f8de350f6729810a74617.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{NAND}$](img/c76af4b04d6208a03309bc0816f22681.png "Rendered by QuickLaTeX.com") | ![$\boldsymbol{NOR}$](img/21bd23c34c06da7832e2c25446a0514e.png "Rendered by QuickLaTeX.com") |
| --- | --- | --- | --- | --- |
| ![$\boldsymbol{w_{1}}$](img/5395183ae22fb2265d43a7298d72c6e7.png "Rendered by QuickLaTeX.com") | one | one | -1 | -1 |
| ![$\boldsymbol{w_{2}}$](img/13d3c0789d566ded5e39d2ec838bc271.png "Rendered by QuickLaTeX.com") | one | one | -1 | -1 |
| ![$\boldsymbol{w_{2}}$](img/13d3c0789d566ded5e39d2ec838bc271.png "Rendered by QuickLaTeX.com") | one | one | -1 | -1 |
| ![$\boldsymbol{b}$](img/c7ccd739aed60032fc89fa01d6512f60.png "Rendered by QuickLaTeX.com") | -2 | -0.9 | three | one |

****Python 实现:****

```
# importing python library
import numpy as np

# sigmoid activation function
def activationFunction(model, type ="sigmoid"):
   return {
       "sigmoid": 1 / (1 + np.exp(-model))
   }[type]

# designing perceptron model
def perceptronModel(weights, inputs, bias):
   model = np.add(np.dot(inputs, weights), bias)
   logic = activationFunction(model, type ="sigmoid")
   return np.round(logic)

# computation model
def compute(data, logicGate, weights, bias):
   weights = np.array(weights)
   output = np.array([ perceptronModel(weights,  
            datum, bias) for datum in data ])
   return output

# Print Output
def printOutput(dataset, name, data):
   print("Logic Function: {}".format(name.upper()))
   print("X1\tX2\tX3\tY")
   toPrint = ["{1}\t{2}\t{3}\t{0}".format(output, *datas)  
              for datas, output in zip(dataset, data)]
   for i in toPrint:
       print(i)

# main function
def main():
   # 3 bit binary data
   dataset = np.array([
     [0, 0, 0],
     [0, 0, 1],
     [0, 1, 0],
     [0, 1, 1],
     [1, 0, 0],
     [1, 0, 1],
     [1, 1, 0],
     [1, 1, 1]
   ])

   # Parameters of every Logic Gates
   # weight parameters: w1, w2, w3
   # bias parameter: b
   logicGate = {
       "and": compute(dataset, "and", [1, 1, 1], -2),
       "or": compute(dataset, "or", [1, 1, 1], -0.9),
       "nand": compute(dataset, "nand", [-1, -1, -1], 3),
       "nor": compute(dataset, "nor", [-1, -1, -1], 1)
   }
   for gate in logicGate:
       printOutput(dataset, gate, logicGate[gate])

if __name__ == '__main__':
   main()
```

****Output:**

```
Logic Function: AND
X1    X2    X3    Y
0    0    0    0.0
0    0    1    0.0
0    1    0    0.0
0    1    1    0.0
1    0    0    0.0
1    0    1    0.0
1    1    0    0.0
1    1    1    1.0
Logic Function: OR
X1    X2    X3    Y
0    0    0    0.0
0    0    1    1.0
0    1    0    1.0
0    1    1    1.0
1    0    0    1.0
1    0    1    1.0
1    1    0    1.0
1    1    1    1.0
Logic Function: NAND
X1    X2    X3    Y
0    0    0    1.0
0    0    1    1.0
0    1    0    1.0
0    1    1    1.0
1    0    0    1.0
1    0    1    1.0
1    1    0    1.0
1    1    1    0.0
Logic Function: NOR
X1    X2    X3    Y
0    0    0    1.0
0    0    1    0.0
0    1    0    0.0
0    1    1    0.0
1    0    0    0.0
1    0    1    0.0
1    1    0    0.0
1    1    1    0.0

```** 

**这里，根据 3 位二进制输入的真值表，每个测试输入的模型预测输出(![$\boldsymbol{\hat{y}}$](img/a6e8955385eea2eb103e7a07d209a00c.png "Rendered by QuickLaTeX.com"))与与门、或门、与非门和或非门常规输出(![$\boldsymbol{y}$](img/2a77d93c3050965e762fdc689edaab6e.png "Rendered by QuickLaTeX.com"))完全匹配。
因此，验证了所有这些逻辑门的感知器算法是正确实现的。**