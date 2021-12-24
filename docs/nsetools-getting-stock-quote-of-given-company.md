# 工具–获取给定公司的股票报价

> 原文:[https://www . geesforgeks . org/nsetools-get-stock-报价-给定公司/](https://www.geeksforgeeks.org/nsetools-getting-stock-quote-of-given-company/)

在本文中，我们将了解如何使用 nsetools 获取给定公司的股票报价。 **Nsetools** 是一个从印度国家证券交易所收集实时数据的库。股票报价是股票在交易所的报价。特定股票的基本报价提供了信息，如其买入价和卖出价、上次交易价格和交易量。

> **获取股票报价的步骤**
> 1。从 nsetools
> 2 导入 Nse。创建一个 Nse 对象
> 3。借助 get_quote 方法从 Nse 对象获取股票报价，股票代码为公司的 NSE 股票代码
> 4。打印股票报价

下面是实现

```
# importing nse from nse tools
from nsetools import Nse

# creating a Nse object
nse = Nse()

# nse stock code for wipro
code = "wipro"

# getting stock quote 
quote = nse.get_quote(code)

# printing quote
print(quote)
```

**输出:**

```
{'pricebandupper': 309.15, 'symbol': 'WIPRO', 'applicableMargin': 19.23, 'bcEndDate': '13-JUL-20', 'totalSellQuantity': None, 'adhocMargin': None, 'companyName': 'Wipro Limited', 'marketType': 'N', 'exDate': '08-JUL-20', 'bcStartDate': '10-JUL-20', 'css_status_desc': 'Listed', 'dayHigh': 284.45, 'basePrice': 281.05, 'securityVar': 15.73, 'pricebandlower': 252.95, 'sellQuantity5': None, 'sellQuantity4': None, 'sellQuantity3': None, 'cm_adj_high_dt': '31-JUL-20', 'sellQuantity2': None, 'dayLow': 277.4, 'sellQuantity1': None, 'quantityTraded': 7345555.0, 'pChange': '-1.05', 'totalTradedValue': 20596.94, 'deliveryToTradedQuantity': 21.36, 'totalBuyQuantity': 610.0, 'averagePrice': 280.4, 'indexVar': None, 'cm_ffm': 41333.68, 'purpose': 'ANNUAL GENERAL MEETING', 'buyPrice2': None, 'secDate': '05-Aug-2020 00:00:00', 'buyPrice1': 278.2, 'high52': 290.8, 'previousClose': 281.05, 'ndEndDate': None, 'low52': 159.4, 'buyPrice4': None, 'buyPrice3': None, 'recordDate': None, 'deliveryQuantity': 1569237.0, 'buyPrice5': None, 'priceBand': 'No Band', 'extremeLossMargin': 3.5, 'cm_adj_low_dt': '19-MAR-20', 'varMargin': 15.73, 'sellPrice1': None, 'sellPrice2': None, 'totalTradedVolume': 7345555.0, 'sellPrice3': None, 'sellPrice4': None, 'sellPrice5': None, 'change': '-2.95', 'surv_indicator': None, 'ndStartDate': None, 'buyQuantity4': None, 'isExDateFlag': False, 'buyQuantity3': None, 'buyQuantity2': None, 'buyQuantity1': 610.0, 'series': 'EQ', 'faceValue': 2.0, 'buyQuantity5': None, 'closePrice': 278.2, 'open': 281.25, 'isinCode': 'INE075A01022', 'lastPrice': 278.1}

```

另一个例子

```
# importing nse from nse tools
from nsetools import Nse

# creating a Nse object
nse = Nse()

# nse stock code for hdfc
code = "hdfcbank"

# getting stock quote 
quote = nse.get_quote(code)

# printing quote
print(quote)
```

**输出:**

```
{'pricebandupper': 1145.8, 'symbol': 'HDFCBANK', 'applicableMargin': 18.2, 'bcEndDate': None, 'totalSellQuantity': None, 'adhocMargin': None, 'companyName': 'HDFC Bank Limited', 'marketType': 'N', 'exDate': '19-SEP-19', 'bcStartDate': None, 'css_status_desc': 'Listed', 'dayHigh': 1055.8, 'basePrice': 1041.65, 'securityVar': 14.7, 'pricebandlower': 937.5, 'sellQuantity5': None, 'sellQuantity4': None, 'sellQuantity3': None, 'cm_adj_high_dt': '19-DEC-19', 'sellQuantity2': None, 'dayLow': 1020.0, 'sellQuantity1': None, 'quantityTraded': 16610696.0, 'pChange': '-1.03', 'totalTradedValue': 172025.35, 'deliveryToTradedQuantity': 26.31, 'totalBuyQuantity': 7009.0, 'averagePrice': 1035.63, 'indexVar': None, 'cm_ffm': 445360.08, 'purpose': 'FACE VALUE SPLIT (SUB-DIVISION) - FROM RS 2 PER SHARE TO RS 1 PER SHARE', 'buyPrice2': None, 'secDate': '05-Aug-2020 00:00:00', 'buyPrice1': 1027.55, 'high52': 1305.5, 'previousClose': 1041.65, 'ndEndDate': None, 'low52': 738.75, 'buyPrice4': None, 'buyPrice3': None, 'recordDate': '20-SEP-19', 'deliveryQuantity': 4369897.0, 'buyPrice5': None, 'priceBand': 'No Band', 'extremeLossMargin': 3.5, 'cm_adj_low_dt': '24-MAR-20', 'varMargin': 14.7, 'sellPrice1': None, 'sellPrice2': None, 'totalTradedVolume': 16610696.0, 'sellPrice3': None, 'sellPrice4': None, 'sellPrice5': None, 'change': '-10.70', 'surv_indicator': None, 'ndStartDate': None, 'buyQuantity4': None, 'isExDateFlag': False, 'buyQuantity3': None, 'buyQuantity2': None, 'buyQuantity1': 7009.0, 'series': 'EQ', 'faceValue': 1.0, 'buyQuantity5': None, 'closePrice': 1027.55, 'open': 1047.95, 'isinCode': 'INE040A01034', 'lastPrice': 1030.95}

```