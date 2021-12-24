# 工具–获取公司的特别保证金

> 原文:[https://www . geesforgeks . org/nsetools-get-ad hoc-margin-of-coma pny/](https://www.geeksforgeeks.org/nsetools-getting-adhoc-margin-of-comapny/)

在本文中，我们将看到如何使用 nsetools 获得给定公司的特别利润。 **Nsetools** 是一个从印度国家证券交易所收集实时数据的库。股票报价是股票在交易所的报价。特定股票的基本报价提供了信息，如其买入价和卖出价、上次交易价格和交易量。证券交易所从未偿头寸过大的会员处收取的临时保证金，或基于临时基础对不稳定脚本征收的保证金，同时考虑风险。

> **获取股票报价的步骤**
> 1。从 nsetools
> 2 导入 Nse。创建一个 Nse 对象
> 3。借助 get_quote 方法从 Nse 对象获取股票报价，股票代码为公司的 NSE 股票代码
> 4。借助“即席保证金”键
> 5 从报价中获取即席保证金。打印临时保证金值

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

# getting adhoc margin
value = quote['adhocMargin']

# printing adhoc margin
print("Adhoc Margin  : " + str(value))
```

**输出:**

```py
Adhoc Margin  : None
```

另一个例子

## 蟒蛇 3

```py
# importing nse from nse tools
from nsetools import Nse

# creating a Nse object
nse = Nse()

# nse stock code for sbi
code = "sbin"

# getting stock quote
quote = nse.get_quote(code)

# getting adhoc margin
value = quote['adhocMargin']

# printing adhoc margin
print("Adhoc Margin  : " + str(value))
```

**输出:**

```py
Adhoc Margin  : 13.02
```