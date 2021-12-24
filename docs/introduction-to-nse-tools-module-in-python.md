# Python 中 NSE 工具模块介绍

> 原文:[https://www . geesforgeks . org/introduction-to-NSE-tools-module-in-python/](https://www.geeksforgeeks.org/introduction-to-nse-tools-module-in-python/)

**NSE** 印度国家证券交易所有限公司是印度领先的证券交易所，位于马哈拉施特拉邦孟买。NSE 成立于 1992 年，是该国第一家非物质化电子交易所。
**n 工具**是一个从印度国家证券交易所收集实时数据的图书馆。它可以用于各种类型的项目，这些项目需要获取给定股票或指数的实时报价，或者构建大型数据集以进行进一步的数据分析。我们还可以构建命令行界面应用程序，以极快的速度为我们提供实时市场详情，比任何浏览器都快得多。数据的准确性仅与 http://www.nseindia.com
上提供的一样正确。为了安装 nse 工具，我们必须使用下面给出的命令

```py
pip install nsetools
```

**创建神经元特异性烯醇化酶对象**

## 蟒蛇 3

```py
# importing nse from nse tools
from nsetools import Nse

# creating a Nse object
nse = Nse()

# printing Nse object
print(nse)
```