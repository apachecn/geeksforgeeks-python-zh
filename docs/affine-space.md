# 仿射空间

> 原文:[https://www.geeksforgeeks.org/affine-space/](https://www.geeksforgeeks.org/affine-space/)

### **仿射空间**

![](img/44605b738c0bd98746fad47dd7e8eb84.png)

仿射空间

仿射空间是具有向量空间的集合 E，是集合 E 上加性空间的传递和自由作用，空间 A 的元素称为点。与仿射空间相关联的向量空间称为自由向量，并且动作+: E * \vec{E} \rightarrow E 满足以下条件:

1.  右标识:a + 0 = a ![\, \forall \, a \,\epsilon \,A](img/73c79a15316f6b05fff0569101d4a189.png "Rendered by QuickLaTeX.com")
2.  关联性:![(a + u) + v = a + (u+v) \, \forall a \, \epsilon \, E \,\, \forall \, \, u, v \, \epsilon \, \vec{E}](img/0adf35026cd11330d57c8f083310707e.png "Rendered by QuickLaTeX.com")
3.  对于任意两点 a，b \εE，存在唯一的 u，使得:

![a + u =b](img/8529b13139c96e6ec89d2b78598b30c9.png "Rendered by QuickLaTeX.com")

其中 u \uε\u vec { E }和可以表示为 *ab* 或\u vec { ab }或有时表示为 b-a。因此，我们可以写出上面的等式

![b= a + ab](img/cc13c7f1da4a0966bdc18d7b024082c4.png "Rendered by QuickLaTeX.com")

### 示例:

。考虑![A^2      ](img/2d48ca5db28eba165c55b0d279c1cb8d.png "Rendered by QuickLaTeX.com")的子集 L，它由满足以下等式的所有点(x，y)组成:

![x+y - 1=0](img/9ee98ce70a98470e3c4d847f5a41982b.png "Rendered by QuickLaTeX.com")

l 是通过点(1，0)和(0，1)的斜率为-1 的直线。通过定义 L 上的 R 的动作+: L * R \rightarrow L，使得 L 上的每个点(x，1-x)和任何 u \εR，线 L 可以是仿射空间

![(x, 1-x) + u = (x+u, 1-x-u)](img/6b8f7ec7d543227df924653c98e11604.png "Rendered by QuickLaTeX.com")

现在，对于 L 上的任意两点 a =(a_1，1- a_1)和 b = (b_1，1-b_1)，唯一向量 u \εR 使得 b = a+u 是 u = b _ 1–a _ 1。注意向量空间 **R** 同构于方程 *x + y = 0* 通过原点的直线。

### 查斯的身份

<center>
![](img/81af626f0784e8058ad1b20bdd9dbb68.png)</center>

给定任意三个点![a,b,c \epsilon     ](img/f554c443ca8d1b63b83d73b6ea8da8b3.png "Rendered by QuickLaTeX.com")，由于 c = a + ac，b = a + ab，c = b + bc，我们得到

![c = b+ bc = a + ab +bc ](img/16682d89b680d266956d35c59ed4a146.png "Rendered by QuickLaTeX.com")

通过应用上述属性 2 和 3，

![ab +bc  = ac](img/77ec3b52c21f04affc3f151b2ec8e1ab.png "Rendered by QuickLaTeX.com")

上述方程被称为 chasles 恒等式。因为

a = a + aa

通过使用属性 1，我们得到

a = a+ 0

因此，通过使用属性 3，我们得到:

![aa=0](img/446d1be67b898a9452c3ff995cdee0c7.png "Rendered by QuickLaTeX.com")

在 Chasles Identity 中用 a 代替 c，我们得到:

ba =-ab

现在，对于 4 个点 a，b，c，d \ε，裂缝的恒等式可以表示为:

ad+bc = ad+ dc = ac

## 仿射组合/重心

类似于线性代数中的线性组合，仿射几何中的相应概念是仿射组合的概念，也称为重心

将 2 维空间视为仿射空间，原点 O= (0，0)和基向量(1，0)和(0，1)。给定任意两点 a =(a1，a2)和 b =(b1，b2)，可以有一个自然的组合，使得\λa+\μb 或:

![(\lambda a_1 + \mu b_1, \lambda a_2 + \mu b_2)](img/6c57b59a9fa7eb13e5d12ea69aef81bc.png "Rendered by QuickLaTeX.com")

当 a = (-1，-1)和 b = (2，2)时，a+b 可以这样给出:c = (1，1)。

现在，考虑相对于原点 c = (1，1)的新坐标系。现在，a 的坐标= (-2，-2)，b 的坐标是(1，1)，d 的点= (-1，-1)。但是，点 d 与第一个坐标系的原点 O = (0，0)相同。

因此，a + b 对应于两个不同的点，这取决于使用哪个坐标系进行计算。这意味着我们需要仿射计算所需的额外条件。结果是标量加起来是 1。这有助于我们定义重心

对于 E 中的任意点族(a _ I)_ { I \εI }，对于任意标量族，使得![\sum_{i \epsilon I } \lambda_i =1   ](img/a808673291db6342eb7634c8e0d2d51a.png "Rendered by QuickLaTeX.com")和任意![a \epsilon E   ](img/8285739e0182e290447b31aef0e5a5d1.png "Rendered by QuickLaTeX.com")点

![a + \sum_{i \epsilon I} \lambda_i a a_i   ](img/d939065efe2436810db9d33f5938a2c9.png "Rendered by QuickLaTeX.com")被称为分配了权重![\lambda_i   ](img/af6ad5c18e02c928c4fdb88cc8ec8275.png "Rendered by QuickLaTeX.com")的点 a_i 的*重心*，由以下等式表示:

![\sum_{i \epsilon E} \lambda_i a_i   ](img/e3cef0e8b667f61af6749439030a753e.png "Rendered by QuickLaTeX.com")。

重心由符号![(a, \lambda)   ](img/bdb29869ab5d0eecc9546036ba349cfd.png "Rendered by QuickLaTeX.com")方便地表示，而![a \epsilon E   ](img/8285739e0182e290447b31aef0e5a5d1.png "Rendered by QuickLaTeX.com")是点，![\lambda \epsilon R   ](img/82e998f81fe179c282ebef1cf722fd52.png "Rendered by QuickLaTeX.com")被称为标量。

### 仿射子空间

<center>
![](img/b8ca664c1bd5182ee0c2340c330df311.png)

v 是![\vec{V} ](img/6c95bd5b24e6ee5995296607f5f09bde.png "Rendered by QuickLaTeX.com")方向上![\vec{E} ](img/b09553ddd4765e6274a3beec83d97e83.png "Rendered by QuickLaTeX.com")的仿射子空间

</center>

给定仿射空间![\left \langle E, \vec{E}, +  \right \rangle   ](img/8bb9cf7d53a3d665dd1edd9046d240af.png "Rendered by QuickLaTeX.com")，E 的子集 V 是![\left \langle E, \vec{E}, +  \right \rangle   ](img/8bb9cf7d53a3d665dd1edd9046d240af.png "Rendered by QuickLaTeX.com")的仿射子空间，如果对于 V 中的每一族加权点![((ai , λi))_{i \epsilon I}   ](img/d6fd1ed621a3dff0944152ee45d7a55d.png "Rendered by QuickLaTeX.com")，使得![\sum_{i \epsilon I} \lambda_i = 1     ](img/8376bd22d6eae7f0a3ca1f5cdf1c26ff.png "Rendered by QuickLaTeX.com")，重心![\sum_{i \epsilon I } \lambda_{i} a_i   ](img/c23a7a45498eab147e3692ae558a1826.png "Rendered by QuickLaTeX.com")属于 V。

### 参考文献:

*   [**仿射空间 upen**](https://www.cis.upenn.edu/~cis610/geombchap2.pdf)