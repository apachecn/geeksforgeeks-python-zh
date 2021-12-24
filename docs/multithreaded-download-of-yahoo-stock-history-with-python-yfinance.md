# 用 Python 多线程下载雅虎股票历史–yfinance

> 原文:[https://www . geesforgeks . org/多线程-下载-雅虎-股票-历史-与-python-yfinance/](https://www.geeksforgeeks.org/multithreaded-download-of-yahoo-stock-history-with-python-yfinance/)

**Yfinance** 是一个 python 包，让我们能够以 python 方式从雅虎财经 API 中获取历史市场数据。所有 Python 开发人员在 yfinance 的帮助下获取数据变得非常容易。

我们可以很容易地从 yfinance 下载历史股票数据，但问题是，这非常耗时。因此，我们使用多线程来掩盖时间。[多线程](https://www.geeksforgeeks.org/multithreading-python-set-1/)让我们可以通过并发执行多个线程来下载大量数据。

## 装置

这个模块没有内置 Python。要安装它，请在终端中键入以下命令。

```py
pip install yfinance
```

让我们一步一步地看这个过程，下面用实现来解释:

**第一步:**获取所有需要的模块

## python 3

```py
import yfinance as yf
```

**第二步:**获取股票历史数据

## 巨蟒

```py
# Get the stocks info
import yfinance as yf

# Ticker is a function responsible
# for fetching the data MSFT is
# representing info about Microsoft
# Corporation
msft = yf.Ticker('MSFT')

# msft.info will return all information
# about microsoft corporation
data = msft.history()

# printing the data
print(data)
```