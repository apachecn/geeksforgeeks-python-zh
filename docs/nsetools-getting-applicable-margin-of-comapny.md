# 工具–获取公司的适用保证金

> 原文:[https://www . geesforgeks . org/nsetools-get-applied-margin-of-coma pny/](https://www.geeksforgeeks.org/nsetools-getting-applicable-margin-of-comapny/)

在本文中，我们将了解如何使用 nsetools 获得给定公司的适用利润率。 **Nsetools** 是一个从印度国家证券交易所收集实时数据的库。股票报价是股票在交易所的报价。特定股票的基本报价提供了信息，如其买入价和卖出价、上次交易价格和交易量。对于以交易换交易-监督部分(TFT-S 部分)的证券，适用的前期保证金率(风险值保证金+极端损失保证金)为 100 %，每笔交易根据该证券的收盘价进行市场标记。

> **获取股票报价的步骤**
> 1。从 nsetools
> 2 导入 Nse。创建一个 Nse 对象
> 3。借助 get_quote 方法从 Nse 对象获取股票报价，股票代码为公司的 NSE 股票代码
> 4。借助‘applicable margin’键
> 5，从报价中获取适用的利润。打印适用的余量值

下面是实现

## 蟒蛇 3

```py
# importing nse from nse tools
from nsetools import Nse

# creating a Nse object
nse = Nse()

# nse stock code for wipro
code = "wipro"

# getting stock quote
quote = nse.get_quote(code)

# getting applicable margin
value = quote['applicableMargin']

# printing applicable margin
print("Applicable Margin  : " + str(value))
```

**输出:**

```py
Applicable Margin  : 19.23
```

另一个例子

## 蟒蛇 3

```py
# importing nse from nse tools
from nsetools import Nse

# creating a Nse object
nse = Nse()

# nse stock code for hdfc
code = "hdfcbank"

# getting stock quote
quote = nse.get_quote(code)

# getting applicable margin
value = quote['applicableMargin']

# printing applicable margin
print("Applicable Margin  : " + str(value))
```

**输出:**

```py
Applicable Margin  : 18.2
```