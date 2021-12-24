# 数据中的多重共线性

> 原文:[https://www.geeksforgeeks.org/multicollinearity-in-data/](https://www.geeksforgeeks.org/multicollinearity-in-data/)

变量应该与自变量有一个稳定的关系。然而，任何无偏的变量都不应该在其他自变量之间具有稳健的相关性。共线性可以是解释变量之间的线性联系。如果两个变量之间有特殊的线性关系，那么它们就是完全共线的。
多重共线性是指在多重相关模型过程中，两个或两个以上的解释变量在某个阶段呈相当线性相关的情况。如果不偏不倚变量之间的相关性好到 1 或-1，我们就有完美的多重共线性。实际上，在信息集的持续时间内，我们并不经常面临理想的多重共线性。更常见的是，当两个或多个无偏变量之间存在近似线性关系时，多重共线性的困难就出现了。
简单来说，多重共线性可以定义为一个事件，其中一个或多个无偏变量相互之间有很强的相关性。在这种情况下，我们通常应该在每个相关的公平变量中只使用一个。
VIF(方差膨胀因子)是多重共线性生活的标志，而 *statsmodel* 给出了一个特征来计算每个实验变量的 VIF 值，大于 10 的值是高度多重共线性的可能生活方式的经验法则。VIF 价格的优秀指导原则如下，VIF = 1 方式不存在相关性，VIF > 1，但< 5 则存在相关性。

![$V F_{i}=1 / 1-R_{i}^{2}$ where $\mathrm{R}^{2}$ is the coefficient of determination of variable.  ](img/facc57f2b9fa35c4ffaee36e01be50f0.png "Rendered by QuickLaTeX.com")

**什么导致多重共线性？**
**主要类型有:**

*   基于数据的多重共线性:由于设计不良的实验、100%观察性的统计或无法操作的数据收集方法。在某些情况下，变量也可能是特别相关的(通常是从纯粹的观察性研究中收集事实的方式)，并且对研究者来说没有错误。出于这个原因，你应该尽可能地进行行为实验，预先设置预测变量的范围。
*   结构多重共线性:因为你，研究者，当他们试图创建新的预测变量时。

**多重共线性的原因也可以包括:**

*   事实不足。在某些情况下，收集额外的统计数据可以解决问题。
*   虚拟变量也可能被错误地使用。例如，研究人员可能无法排除一个类别，或者为每个类别添加一个虚拟变量(例如，春季、夏季、秋季、冬季。
*   在回归中包含一个混合了其他变量的变量。例如，由“一般投资利润”组成，而总投资收入=股票和债券收益+储蓄利息收益。
*   包括相同(或几乎相同)的变量。例如，以磅为单位的体重和以千克为单位的体重，或者投资收益和储蓄/债券收益。

**例:你也可以定位到多重共线性可能是测试制定计划的一个特征。**
在材料制造商的案例中，我们可以毫无问题地看到，广告、营销和数量是相关的预测变量，主要是营销影响中的波动，而数量包括在版本中，也不包括在版本中。在一个类似的测试中，你会发现产品生产商可能会额外引入数量和广告之间的多重共线性，因为这是实验设计的一部分，使用分配一个过大的广告价格范围给商店较小的城市，一个浓缩咖啡广告资助给商店较大的城市。
如果你准备好重新做市场测试，你将通过重组实验来解决这个困难，以确保过度广告/低量、过度广告/高量、低广告/高量和低广告/低量商店的诚实集合。这可以让您消除事实集中的多重共线性。然而，重新做一个实验通常是不可能的。这就是为什么在开始之前非常谨慎地分析受控实验的计划是至关重要的，这样你就可以避免偶然引起这样的问题。如果你因为实验设计而找到了多重共线性，并且你不能重新做实验，你将通过包括控制来处理多重共线性。在布料生产商的情况下，在版本中加入范围是至关重要的，这样可以促使对广告的影响做出更高的正确估计。在这种情况下，解决多重共线性的其他答案包括收缩估计，如主成分回归或偏最小二乘分析。
**代码:Python 代码，使用 VIF 因子去除数据集中的多重共线性。**

## 蟒蛇 3

```py
# read the dataset
import pandas as pd
data = pd.read_csv('https://docs.google.com / spreadsheets / d/e / 2PACX-1vQRtMKSAzDVoUFeP_lvpxSPt0pb7YR3_SPBdnq0_2nIgfZUMB8fMgJXaMETqLmrV3uw2yOqkZLEcTvt / pub?output = csv')
data.head(3)

# Remove the price from the dataset
Y = data["price"]
iv = data.columns
iv = iv.delete(0)
X = data[iv]

# calculate the variance inflation factor
from statsmodels.stats.outliers_influence import variance_inflation_factor as vif

# compare with each column
[vif(data[iv].values, index) for index in range(len(iv))]

# Removing multicollinearity from the dataset using vif
from statsmodels.stats.outliers_influence import variance_inflation_factor as vif

# compare with each columns
for i in range(len(iv)):
    vif_list = [vif(data[iv].values, index) for index in range(len(iv))]
    maxvif = max(vif_list)
    print("Max VIF value is ", maxvif)                     
    drop_index = vif_list.index(maxvif)
    print("For Independent variable", iv[drop_index])

    if maxvif > 10:

        print("Deleting", iv[drop_index])
        iv = iv.delete(drop_index)
        print("Final Independent_variables ", iv)
```

**输出:**

```py
Max VIF value is  15.213540834822062
For Independent variable bedrooms
Deleting bedrooms
Final Independent_variables  Index(['lotsize', 'bathrms', 'stories', 'driveway', 'recroom', 'fullbase',
       'gashw', 'airco', 'garagepl', 'prefarea'],
      dtype='object')
Max VIF value is  7.738793387948324
For Independent variable bathrms
Max VIF value is  7.738793387948324
For Independent variable bathrms
Max VIF value is  7.738793387948324
For Independent variable bathrms
Max VIF value is  7.738793387948324
For Independent variable bathrms
Max VIF value is  7.738793387948324
For Independent variable bathrms
Max VIF value is  7.738793387948324
For Independent variable bathrms
Max VIF value is  7.738793387948324
For Independent variable bathrms
Max VIF value is  7.738793387948324
For Independent variable bathrms
Max VIF value is  7.738793387948324
For Independent variable bathrms
Max VIF value is  7.738793387948324
For Independent variable bathrms
```

我们可以注意到，VIF 分析已经删除了大于 10 的卧室，但是保留了第一层和第二层。为了测试模型的性能，通常的做法是将数据集分成 80/20(或 70/30)分别用于训练/测试，并使用训练数据集来构建模型，然后将训练好的模型应用于测试数据集来评估模型的性能。我们还可以通过寻找 r2 得分来评估模型的性能。