# ANN–双向联想记忆(BAM)学习算法

> 原文:[https://www . geesforgeks . org/ann-双向-联想-记忆-bam-学习-算法/](https://www.geeksforgeeks.org/ann-bidirectional-associative-memory-bam-learning-algorithm/)

**先决条件:** [ANN |双向联想记忆(BAM)](https://www.geeksforgeeks.org/ann-bidirectional-associative-memory-bam/)

构建 BAM 模型有三个主要步骤。

1.  学问
2.  测试
3.  检索

在《人工神经网络|双向联想记忆》一文中，每一步都用数学公式进行了描述。

**这里用一个例子迭代说明这个学习算法。**
假设，
集合 A:输入模式

![\[$\operatorname{Set} \boldsymbol{A}: X_{1}=\left[\begin{array}{c}1 \\ 1 \\ 1 \\ 1 \\ 1 \\ 1\end{array}\right] \quad X_{2}=\left[\begin{array}{c}-1 \\ -1 \\ -1 \\ -1 \\ -1 \\ -1\end{array}\right] \quad X_{3}=\left[\begin{array}{r}1 \\ 1 \\ -1 \\ -1 \\ 1 \\ 1\end{array}\right] \quad X_{4}=\left[\begin{array}{r}-1 \\ -1 \\ 1 \\ 1 \\ -1 \\ -1\end{array}\right]$\]](img/ae526f05096e492ba6e2888b49e4c5e1.png "Rendered by QuickLaTeX.com")

集合 B:对应的目标模式

![\[$\operatorname{Set} \mathbf{B}: Y_{1}=\left[\begin{array}{l}1 \\ 1 \\ 1\end{array}\right] \quad Y_{2}=\left[\begin{array}{r}-1 \\ -1 \\ -1\end{array}\right] \quad Y_{3}=\left[\begin{array}{r}1 \\ -1 \\ 1\end{array}\right] \quad Y_{4}=\left[\begin{array}{r}-1 \\ 1 \\ -1\end{array}\right]$\]](img/a012e1b7c2a67ba0146ab12e7648a592.png "Rendered by QuickLaTeX.com")

***第一步:*** 这里，M(图案对数)的值为 4。
***第二步:*** 分配输入输出层的神经元。这里，输入层的神经元是 6 个，输出层是 3 个

***第三步:*** 现在，计算权重矩阵(W):

![\[$\begin{aligned} W=\left[\begin{array}{l}1 \\ 1 \\ 1 \\ 1 \\ 1 \\ 1\end{array}\right]\left[\begin{array}{lll}1 & 1 & 1\end{array}\right]+\left[\begin{array}{lll}-1 \\ -1 \\ -1 \\ -1 \\ -1 \\ -1\end{array}\right]\left[\begin{array}{lll}-1 & -1 & -1\end{array}\right]+\left[\begin{array}{r}1 \\ 1 \\ -1 \\ -1 \\ 1 \\ 1\end{array}\right]\left[\begin{array}{llll}1 & -1 & 1\end{array}\right]+\left[\begin{array}{r}-1 \\ -1 \\ 1 \\ 1 \\ -1 \\ -1\end{array}\right]\left[\begin{array}{lll}-1 & 1 & -1\end{array}\right]\] \[=\left[\begin{array}{lll}4 & 0 & 4 \\ 4 & 0 & 4 \\ 0 & 4 & 0 \\ 0 & 4 & 0 \\ 4 & 0 & 4 \\ 4 & 0 & 4\end{array}\right] \end{aligned}$\]](img/5be65e81412bea52d0e15338961aaf87.png "Rendered by QuickLaTeX.com")

***第四步:*** 测试 BAM 模型学习算法——对于输入模式 BAM 会返回相应的目标模式作为输出。对于每个目标模式，BAM 将返回相应的输入模式。

*   Test on input patterns (Set A) using-

    ![\[Y_{m}=\operatorname{sign}\left(W^{T} X_{m}\right), \quad m=1.2, \ldots, M\]](img/1a53a3a09b029dde2f9afc43d6e602a2.png "Rendered by QuickLaTeX.com")

    ![ \[$\boldsymbol{Y}_{1}=\operatorname{sign}\left(\boldsymbol{W}^{T} \boldsymbol{X}_{1}\right)=\operatorname{sign}\left\{\left[\begin{array}{cccccc}\mathbf{4} & \mathbf{4} & \mathbf{0} & \mathbf{0} & \mathbf{4} & \mathbf{4} \\ \mathbf{0} & \mathbf{0} & \mathbf{4} & \mathbf{4} & \mathbf{0} & \mathbf{0} \\ \mathbf{4} & \mathbf{4} & \mathbf{0} & \mathbf{0} & \mathbf{4} & \mathbf{4}\end{array}\right]\left[\begin{array}{c}\mathbf{1} \\ \mathbf{1} \\ \mathbf{1} \\ \mathbf{1} \\ \mathbf{1} \\ \mathbf{1}\end{array}\right]\right\}=\left[\begin{array}{c}\mathbf{1} \\ \mathbf{1} \\ \mathbf{1}\end{array}\right]$\] \[$\boldsymbol{Y}_{2}=\operatorname{sign}\left(\boldsymbol{W}^{T} \boldsymbol{X}_{2}\right)=\operatorname{sign}\left\{\left[\begin{array}{cccccc}\mathbf{4} & \mathbf{4} & \mathbf{0} & \mathbf{0} & \mathbf{4} & \mathbf{4} \\ \mathbf{0} & \mathbf{0} & \mathbf{4} & \mathbf{4} & \mathbf{0} & \mathbf{0} \\ \mathbf{4} & \mathbf{4} & \mathbf{0} & \mathbf{0} & \mathbf{4} & \mathbf{4}\end{array}\right]\left[\begin{array}{c}\mathbf{-1} \\ \mathbf{-1} \\ \mathbf{-1} \\ \mathbf{-1} \\ \mathbf{-1} \\ \mathbf{-1}\end{array}\right]\right\}=\left[\begin{array}{c}\mathbf{-1} \\ \mathbf{-1} \\ \mathbf{-1}\end{array}\right]$\] \[$\boldsymbol{Y}_{3}=\operatorname{sign}\left(\boldsymbol{W}^{T} \boldsymbol{X}_{3}\right)=\operatorname{sign}\left\{\left[\begin{array}{cccccc}\mathbf{4} & \mathbf{4} & \mathbf{0} & \mathbf{0} & \mathbf{4} & \mathbf{4} \\ \mathbf{0} & \mathbf{0} & \mathbf{4} & \mathbf{4} & \mathbf{0} & \mathbf{0} \\ \mathbf{4} & \mathbf{4} & \mathbf{0} & \mathbf{0} & \mathbf{4} & \mathbf{4}\end{array}\right]\left[\begin{array}{c}\mathbf{1} \\ \mathbf{1} \\ \mathbf{-1} \\ \mathbf{-1} \\ \mathbf{1} \\ \mathbf{1}\end{array}\right]\right\}=\left[\begin{array}{c}\mathbf{1} \\ \mathbf{-1} \\ \mathbf{1}\end{array}\right]$\] \[$\boldsymbol{Y}_{4}=\operatorname{sign}\left(\boldsymbol{W}^{T} \boldsymbol{X}_{4}\right)=\operatorname{sign}\left\{\left[\begin{array}{cccccc}\mathbf{4} & \mathbf{4} & \mathbf{0} & \mathbf{0} & \mathbf{4} & \mathbf{4} \\ \mathbf{0} & \mathbf{0} & \mathbf{4} & \mathbf{4} & \mathbf{0} & \mathbf{0} \\ \mathbf{4} & \mathbf{4} & \mathbf{0} & \mathbf{0} & \mathbf{4} & \mathbf{4}\end{array}\right]\left[\begin{array}{c}\mathbf{-1} \\ \mathbf{-1} \\ \mathbf{1} \\ \mathbf{1} \\ \mathbf{-1} \\ \mathbf{-1}\end{array}\right]\right\}=\left[\begin{array}{c}\mathbf{-1} \\ \mathbf{1} \\ \mathbf{-1}\end{array}\right]$\] ](img/9ae0ca68e78404a1f77e5735b51d2c40.png "Rendered by QuickLaTeX.com")

*   Test on target patterns (Set B) using-

    ![\[X_{m}=\operatorname{sign}\left(W Y_{m}\right), \quad m=1.2, \ldots, M\]](img/1e50c2615965586680d4d7d37013ce45.png "Rendered by QuickLaTeX.com")

    ![ \[$\boldsymbol{X}_{1}=\operatorname{sign}\left(\boldsymbol{W} \boldsymbol{Y}_{1}\right)=\operatorname{sign}\left\{\left[\begin{array}{ccc}\mathbf{4} & \mathbf{0} & \mathbf{4} \\ \mathbf{4} & \mathbf{0} & \mathbf{4} \\ \mathbf{0} & \mathbf{4} & \mathbf{0} \\ \mathbf{0} & \mathbf{4} & \mathbf{0} \\ \mathbf{4} & \mathbf{0} & \mathbf{4} \\ \mathbf{0} & \mathbf{4} & \mathbf{0}\end{array}\right]\left[\begin{array}{c}\mathbf{1} \\ \mathbf{1} \\ \mathbf{1}\end{array}\right]\right\}=\left[\begin{array}{c}\mathbf{1} \\ \mathbf{1} \\ \mathbf{1} \\ \mathbf{1} \\ \mathbf{1} \\ \mathbf{1}\end{array}\right]$\] \[$\boldsymbol{X}_{2}=\operatorname{sign}\left(\boldsymbol{W} \boldsymbol{Y}_{2}\right)=\operatorname{sign}\left\{\left[\begin{array}{ccc}\mathbf{4} & \mathbf{0} & \mathbf{4} \\ \mathbf{4} & \mathbf{0} & \mathbf{4} \\ \mathbf{0} & \mathbf{4} & \mathbf{0} \\ \mathbf{0} & \mathbf{4} & \mathbf{0} \\ \mathbf{4} & \mathbf{0} & \mathbf{4} \\ \mathbf{0} & \mathbf{4} & \mathbf{0}\end{array}\right]\left[\begin{array}{c}\mathbf{-1} \\ \mathbf{-1} \\ \mathbf{-1}\end{array}\right]\right\}=\left[\begin{array}{c}\mathbf{-1} \\ \mathbf{-1} \\ \mathbf{-1} \\ \mathbf{-1} \\ \mathbf{-1} \\ \mathbf{-1}\end{array}\right]$\] \[$\boldsymbol{X}_{3}=\operatorname{sign}\left(\boldsymbol{W} \boldsymbol{Y}_{3}\right)=\operatorname{sign}\left\{\left[\begin{array}{ccc}\mathbf{4} & \mathbf{0} & \mathbf{4} \\ \mathbf{4} & \mathbf{0} & \mathbf{4} \\ \mathbf{0} & \mathbf{4} & \mathbf{0} \\ \mathbf{0} & \mathbf{4} & \mathbf{0} \\ \mathbf{4} & \mathbf{0} & \mathbf{4} \\ \mathbf{0} & \mathbf{4} & \mathbf{0}\end{array}\right]\left[\begin{array}{c}\mathbf{1} \\ \mathbf{-1} \\ \mathbf{1}\end{array}\right]\right\}=\left[\begin{array}{c}\mathbf{1} \\ \mathbf{1} \\ \mathbf{-1} \\ \mathbf{-1} \\ \mathbf{1} \\ \mathbf{1}\end{array}\right]$\] \[$\boldsymbol{X}_{4}=\operatorname{sign}\left(\boldsymbol{W} \boldsymbol{Y}_{4}\right)=\operatorname{sign}\left\{\left[\begin{array}{ccc}\mathbf{4} & \mathbf{0} & \mathbf{4} \\ \mathbf{4} & \mathbf{0} & \mathbf{4} \\ \mathbf{0} & \mathbf{4} & \mathbf{0} \\ \mathbf{0} & \mathbf{4} & \mathbf{0} \\ \mathbf{4} & \mathbf{0} & \mathbf{4} \\ \mathbf{0} & \mathbf{4} & \mathbf{0}\end{array}\right]\left[\begin{array}{c}\mathbf{-1} \\ \mathbf{1} \\ \mathbf{-1}\end{array}\right]\right\}=\left[\begin{array}{c}\mathbf{-1} \\ \mathbf{-1} \\ \mathbf{1} \\ \mathbf{1} \\ \mathbf{-1} \\ \mathbf{-1}\end{array}\right]$\] ](img/90a3544e2be47f3f52ff39ab69edd7a8.png "Rendered by QuickLaTeX.com")

这里，对于每个输入模式，BAM 模型将给出正确的目标模式，对于目标模式，模型也将给出相应的输入模式。
这表示内存或模型网络中的双向关联。