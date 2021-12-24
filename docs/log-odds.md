# 记录赔率

> 原文:[https://www.geeksforgeeks.org/log-odds/](https://www.geeksforgeeks.org/log-odds/)

**几率(成功几率):**定义为成功几率除以失败几率。比方说，有 90%的概率赢得赌注意味着*“赔率对我们有利”*，因为赢的赔率是 90%，而输的赔率只有 10%。它也以比率的形式被称为优势比。所以上面讨论的例子的奇数比率是:

<center>![Odds\ Ratio = \frac{odds\ of\ success}{odds\ of\ failure} = \frac{90}{10} = 9](img/5cfdd8fecb219747b15685141ac00fbf.png "Rendered by QuickLaTeX.com")</center>

形式上，事件 A 的赔率定义为 A 发生的概率对 A 不发生的概率(即 A 的补数)。(如下式所示)

<center>![Odds\ Ratio = \frac{P(A)}{1-P(A)} =\frac{P(A)}{P(A')}](img/bdea553b4efdf5b080bc3cd0985d9c73.png "Rendered by QuickLaTeX.com")</center>

**赔率，不等于概率**

需要注意的是，事件发生的几率与其发生的概率不同。假设我的篮球队赢得锦标赛的概率是 1 比 5。

我的队伍获胜的概率= ![\frac{1}{5} = 0.2   ](img/cc0a54d83d056f2a776c4b7f6636b5d9.png "Rendered by QuickLaTeX.com")但是，
我的队伍获胜的概率= ![\frac{1}{6} = 0.16](img/db9a807774530e225f1a188bd7c60007.png "Rendered by QuickLaTeX.com")

然而，在数学上，两者的最终结果是一样的，因为在概率的情况下，分母被抵消了。(如下图所示)

<center>![Odds = \frac{P(win)}{P(loss)} = \frac{\frac{1}{6}}{\frac{5}{6}} = \frac{1}{5}](img/0b700cd0c55d4ac15527714e1fc562ab.png "Rendered by QuickLaTeX.com")</center>

**赔率问题**

赔率的问题是由于赢的几率和输的几率之间存在不对称。让我们借助一个例子来试着理解这一点。72 个国家参加英联邦运动会。

考虑到每个国家都有相同的获胜机会，印度队赢得金牌的概率是相反的，1 比 71 或![\frac{1}{71} = 0.014   ](img/1d3cfdc91bc1c7b492d7127127bfb33c.png "Rendered by QuickLaTeX.com")
但是假设一个理想主义的场景，印度队赢得金牌的概率是有利的，71 比 1 或![\frac{71}{1} = 71](img/af509bdf48bfc1d6b4f1980020147471.png "Rendered by QuickLaTeX.com")

![](img/c1046b42e9ff3d687d4b60b12e822830.png)

**图 1:有利对不利的领域**

如图 1 所示，当赔率对我们不利时，该值总是位于 0 和 1 之间，这是一个非常小的值。然而，如果赔率对我们有利，这个值可以在 1 到无穷大之间，这可能是一个非常大的值！为了解决这个问题，对数赔率的概念应运而生。

**对数赔率**:是赔率的对数。(如下式所示)

<center>![Log\ Odds = \log(\frac{P(A)}{1-P(A)})](img/e0cc83ec17a95b2a44e21cc31e058abc.png "Rendered by QuickLaTeX.com")</center>

根据上述例子，

印度队赢得一枚金牌的赔率是 1 比 71 = ![\log(\frac{1}{71}) = -1.85](img/e6c980a6ee696e6ee4a623c00bdafbc3.png "Rendered by QuickLaTeX.com")

印度队赢得金牌的概率为 71 比 1 = ![\log(\frac{71}{1}) = 1.85](img/f2c139486c9b4e45332af1facd1aa269.png "Rendered by QuickLaTeX.com")

![](img/bcc6b9c6b47e419cc0e7aaee2031d32b.png)

**图 2:对数赔率**

如图 2 所示，采用比值比的对数会使结果具有一定的对称性，从而更容易在各种统计中进行解释和使用。

> **有趣的注意:**当绘制在柱状图上时，某一事件的对数赔率给出了**正态分布**！这就是对数赔率如此有用的原因。

**真实例子**

对数赔率在医学研究中用于根据受试者以前的症状预测其可能出现的症状。考虑下面的例子。对 1000 名随机出现发热和咳嗽/感冒症状的受试者进行了医学研究。目的是找出咳嗽/感冒的人更有可能发烧或不发烧的可能性。(数据如下图 3 所示。)

![](img/328f522a4dfd3c3b7fe263e83135074f.png)

**图 3:样本研究数据**

**解决方案:**

一个人可能/感冒，也发烧的几率![=\frac{350}{250} = 1.4](img/767474b23c794457626b13fc0180cfe1.png "Rendered by QuickLaTeX.com")

一个没有感冒的人也发烧的几率![=\frac{25}{375} = 0.066](img/07b90c057a8a05ddce9fd60b8209a4c7.png "Rendered by QuickLaTeX.com")

∴客观赔率![=\frac{1.4}{0.066} = 21](img/3fc5d08031f26d621e2989d42ae4f6ea.png "Rendered by QuickLaTeX.com")

和![\log(21) = 1.322  ](img/15061f9c29d6b70992570861bcd74021.png "Rendered by QuickLaTeX.com")，为可以从研究中获得的各种结果提供对称性。

这表明咳嗽/感冒的人也发烧的可能性**是不咳嗽/感冒的人的**的 21 倍。对数优势或优势比非常类似于 R 平方检验，因为它说明了两个因素之间的关系。所以，可以说，赔率值越高，这两个因素往往越相关。这就是对数优势比的力量。