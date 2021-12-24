# 工具–获取公司股票的基价

> 原文:[https://www . geeksforgeeks . org/nsetools-get-base-coma pny-price-stock/](https://www.geeksforgeeks.org/nsetools-getting-base-price-of-comapny-stock/)

在本文中，我们将了解如何使用 nsetools 获得给定公司的平均价格。 **Nsetools** 是一个从印度国家证券交易所收集实时数据的库。股票报价是股票在交易所的报价。特定股票的基本报价提供了信息，如其买入价和卖出价、上次交易价格和交易量。基础市场价值是一个价值加权指数，由在任何给定时间交易的指数中的所有证券组成。基本市值有助于确定股票市值或指数的价值。基础价值被认为是一个交易所的股票和证券市场的脉搏。

> **获取股票报价的步骤**
> 1。从 nsetools
> 2 导入 Nse。创建一个 Nse 对象
> 3。借助 get_quote 方法从 Nse 对象获取股票报价，股票代码为公司的 NSE 股票代码
> 4。借助“基本价格”键
> 5 从报价中获取基本价格。打印基础价格值

下面是实现

## 蟒蛇 3

```
# importing nse from nse tools
from nsetools import Nse

# creating a Nse object
nse = Nse()

# nse stock code for wipro
code = "wipro"

# getting stock quote
quote = nse.get_quote(code)

# getting base price
value = quote['basePrice']

# printing base price
print("Base Price  : " + str(value))
```

**输出:**

```
Base Price  : 281.05
```

另一个例子

## 蟒蛇 3

```
# importing nse from nse tools
from nsetools import Nse

# creating a Nse object
nse = Nse()

# nse stock code for sbi
code = "sbin"

# getting stock quote
quote = nse.get_quote(code)

# getting base price
value = quote['basePrice']

# printing base price
print("Base Price  : " + str(value))
```

**输出:**

```
Base Price  : 191.6
```