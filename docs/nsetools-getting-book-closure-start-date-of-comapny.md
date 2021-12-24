# n 工具–获取公司的结账开始日期

> 原文:[https://www . geesforgeks . org/nsetools-get-book-close-start-of-date-coma pny/](https://www.geeksforgeeks.org/nsetools-getting-book-closure-start-date-of-comapny/)

在本文中，我们将了解如何使用 nsetools 获取给定公司的结账开始日期。 **Nsetools** 是一个从印度国家证券交易所收集实时数据的库。股票报价是股票在交易所的报价。特定股票的基本报价提供了信息，如其买入价和卖出价、上次交易价格和交易量。账簿关闭是指公司不会处理股东名册调整或股份转让请求的一段时间。公司通常会使用账面关闭日期来确定截止日期，以确定哪些有记录的投资者将在该期间获得股息支付。

> **获取股票报价的步骤**
> 1。从 nsetools
> 2 导入 Nse。创建一个 Nse 对象
> 3。借助 get_quote 方法从 Nse 对象获取股票报价，股票代码为公司的 NSE 股票代码
> 4。借助【bcStartDate】键
> 5，从报价中获取结账开始日期。打印图书关闭开始值

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

# getting book closure start date
value = quote['bcStartDate']

# printing book closure start date
print("Book closure Start date  : " + str(value))
```

**输出:**

```py
Book closure Start date  : 10-JUL-20
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

# getting book closure start date
value = quote['bcStartDate']

# printing book closure start date
print("Book closure Start date  : " + str(value))
```

**输出:**

```py
Book closure Start date  : 19-JUN-18
```