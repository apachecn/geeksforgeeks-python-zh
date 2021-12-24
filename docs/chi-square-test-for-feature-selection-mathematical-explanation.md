# 特征选择卡方检验–数学解释

> 原文:[https://www . geesforgeks . org/chi-square-测试-特征选择-数学-解释/](https://www.geeksforgeeks.org/chi-square-test-for-feature-selection-mathematical-explanation/)

任何有监督机器学习风险中涉及的主要任务之一是从给定的数据集中选择最佳特征以获得最佳结果。选择这些特征的一种方法是卡方检验。

数学上，卡方检验是对两个分布进行的，这两个分布决定了它们各自方差的相似程度。在其**零假设**中，它假设给定的分布是独立的。因此，通过确定输出类标签最依赖的要素，该测试可用于确定给定数据集的最佳要素。对于数据集中的每个要素，计算![\chi ^{2}](img/7645903d1f6d184a738a2562fe589989.png "Rendered by QuickLaTeX.com")，然后根据![\chi ^{2}](img/7645903d1f6d184a738a2562fe589989.png "Rendered by QuickLaTeX.com")值按降序排列。![\chi ^{2}](img/7645903d1f6d184a738a2562fe589989.png "Rendered by QuickLaTeX.com")的值越高，输出标签对特征的依赖性就越强，特征对确定输出的重要性就越高。

让所讨论的特征有 m 个属性值，输出有 k 个类标签。那么![\chi ^{2}](img/7645903d1f6d184a738a2562fe589989.png "Rendered by QuickLaTeX.com")的值由以下表达式给出:-

![\chi ^{2} = \sum _{i=1}^{m} \sum _{j=1}^{k}\frac{(O_{ij}-E_{ij})^{2}}{E_{ij}}](img/0082c657b762ac0c0bba1297c44f1fb3.png "Rendered by QuickLaTeX.com")

在哪里

![O_{ij}](img/cd9cae04423d90db157e5e48c8d9c9d6.png "Rendered by QuickLaTeX.com")–观察频率

![E_{ij}](img/76b163e12ec0de87f164551692c63293.png "Rendered by QuickLaTeX.com")–预期频率

对于每个特征，创建一个包含 m 行和 k 列的应急表。每个单元格(I，j)表示属性特征为 I、类别标签为 k 的行数。因此，该表中的每个单元格表示观察到的频率。要计算每个像元的预期频率，首先计算要素值在总数据集中的比例，然后将其乘以当前类别标签的总数。

**已解决示例:**

请考虑下表

![](img/a7d46b33b1f293d3a7e60b1d3ad3cd88.png)

这里的输出变量是名为“PlayTennis”的列，它决定了在给定的天气条件下是否在给定的一天打网球。

功能“展望”的应急表构建如下

![](img/35fb3dfbb2baec65682bb7db789763e8.png)

请注意，括号内给出了每个单元格的预期值。

单元格的期望值(晴天，是)计算为![\frac{5}{14}\times 9 = 3.21](img/6b620e780a26118185ff8ac9b254e972.png "Rendered by QuickLaTeX.com")，其他单元格也是如此。

![\chi ^{2}_{outlook}](img/63ece801881a6abba87b0a8fa610db59.png "Rendered by QuickLaTeX.com")值计算如下:-

![\chi ^{2}_{outlook} = \frac{(2-3.21)^{2}}{3.21}+\frac{(3-1.79)^{2}}{1.79}+\frac{(4-2.57)^{2}}{2.57}+\frac{(0-1.43)^{2}}{1.43}+\frac{(3-3.21)^{2}}{3.21}+\frac{(2-1.79)^{2}}{1.79}](img/bdc62cab2638a0d57e52c216cd4dd15e.png "Rendered by QuickLaTeX.com")

![\Rightarrow \chi ^{2}_{outlook} = 3.129](img/16aa9a91ea26210213e94bfa5c3eff82.png "Rendered by QuickLaTeX.com")

特征“风”的应急表如下所示

![](img/a0589c3f3b853a1a8a3bb9de1aa51575.png)

![\chi ^{2}_{wind}](img/46d96f9fe62d1789b462a489dad6d6ca.png "Rendered by QuickLaTeX.com")值计算如下:-

![\chi ^{2}_{wind} = \frac{(3-3.86)^{2}}{3.86}+\frac{(3-1.14)^{2}}{1.14}+\frac{(6-5.14)^{2}}{5.14}+\frac{(2-2.86)^{2}}{2.86}](img/708613268584531da98d4856d46c87dd.png "Rendered by QuickLaTeX.com")

![\Rightarrow \chi ^{2}_{wind} = 3.629](img/1652c008ccf282c5b4565260d96c443b.png "Rendered by QuickLaTeX.com")

通过比较这两个分数，我们可以得出结论，特征“Wind”比特征“Outlook”对确定输出更重要。

[本文](https://www.geeksforgeeks.org/ml-chi-square-test-for-feature-selection/)演示如何使用卡方检验进行特征选择。