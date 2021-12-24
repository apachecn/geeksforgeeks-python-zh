# 使用 Python 中的 mplfinance 模块绘制烛台图

> 原文:[https://www . geesforgeks . org/plot-烛台-图表-使用-mpl finance-python 中的模块/](https://www.geeksforgeeks.org/plot-candlestick-chart-using-mplfinance-module-in-python/)

**烛台图**也被称为日式图表。这些被广泛用于交易中的技术分析，因为它们可视化了一段时间内的价格规模。他们有四个点开放，高，低，关闭( **OHLC** )。可以使用名为 **mplfinance** 的 matplotlib 模块用 python 创建烛台图表。

#### **安装:**

```py
pip install mplfinance
```

## mplfinance .烛台 _ohlc()

该功能用于绘制**烛台图表。**

> **语法:** mplfinance .烛台 _ohlc(ax，引号，宽度=0.2，colorup='k '，colordown='r '，alpha=1.0)
> **参数:**
> 
> *   **轴:**要绘制到的轴实例。
> *   **报价:**序列(时间、开盘、高、低、收盘、…)序列。
> *   **宽度:**矩形宽度一天的分数。
> *   **上色:**闭合处矩形的颜色> =打开。
> *   **淡化:**关闭的矩形的颜色<打开。
> *   **alpha:** (浮动)矩形 alpha 级别。
> 
> **返回:**返回(线、面片)，其中线是添加的线的列表，面片是添加的矩形面片的列表。

为了绘制图表，我们将从 [NSE](https://www1.nseindia.com/products/content/equities/indices/historical_index_data.htm) 获取 2020 年 01-07 月至 2020 年 15-07 月期间的数据，这些数据可以在 csv 文件中下载，也可以从[这里的](https://docs.google.com/spreadsheets/d/1QGx0q7vnMRTT8S2MKeYg7YSc9oQTswPEDpy3EDEV48g/edit?usp=sharing)下载。对于本例，它被保存为“data.csv”。
我们将使用熊猫库从 data.csv 中提取用于绘图的数据

下面是实现:

## 蟒蛇 3

```py
# import required packages
import matplotlib.pyplot as plt
from mplfinance import candlestick_ohlc
import pandas as pd
import matplotlib.dates as mpdates

plt.style.use('dark_background')

# extracting Data for plotting
df = pd.read_csv('data.csv')
df = df[['Date', 'Open', 'High',
         'Low', 'Close']]

# convert into datetime object
df['Date'] = pd.to_datetime(df['Date'])

# apply map function
df['Date'] = df['Date'].map(mpdates.date2num)

# creating Subplots
fig, ax = plt.subplots()

# plotting the data
candlestick_ohlc(ax, df.values, width = 0.6,
                 colorup = 'green', colordown = 'red',
                 alpha = 0.8)

# allow grid
ax.grid(True)

# Setting labels
ax.set_xlabel('Date')
ax.set_ylabel('Price')

# setting title
plt.title('Prices For the Period 01-07-2020 to 15-07-2020')

# Formatting Date
date_format = mpdates.DateFormatter('%d-%m-%Y')
ax.xaxis.set_major_formatter(date_format)
fig.autofmt_xdate()

fig.tight_layout()

# show the plot
plt.show()
```

**输出:**

![Candlestick Chart](img/3ff6aef8337a70d27af5f2e227fbc622.png)

烛台图表