# n 工具–获取公司股票的平均价格

> 原文:[https://www . geeksforgeeks . org/nsetools-get-coma pny-stock-均价/](https://www.geeksforgeeks.org/nsetools-getting-average-price-of-comapny-stock/)

在本文中，我们将了解如何使用 nsetools 获得给定公司的平均价格。 **Nsetools** 是一个从印度国家证券交易所收集实时数据的库。股票报价是股票在交易所的报价。特定股票的基本报价提供了信息，如其买入价和卖出价、上次交易价格和交易量。对于一只给定的股票，将所有股票的总购买价格相加，然后加上任何已经再投资的股息，再将这个总数除以拥有的股票总数。这将给你每股的平均成本。

> **获取股票报价的步骤**
> 1。从 nsetools
> 2 导入 Nse。创建一个 Nse 对象
> 3。借助 get_quote 方法从 Nse 对象获取股票报价，股票代码为公司的 NSE 股票代码
> 4。借助【平均价格】键
> 5 从报价中获取平均价格。打印平均价格值

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

# getting average price
value = quote['averagePrice']

# printing average price
print("Average Price  : " + str(value))
```

**输出:**

```py
Average Price  : 280.4
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

# getting average price
value = quote['averagePrice']

# printing average price
print("Average Price  : " + str(value))
```

**输出:**

```py
Average Price  : 193.9
```