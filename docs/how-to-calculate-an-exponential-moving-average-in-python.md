# 如何用 Python 计算指数移动平均线？

> 原文:[https://www . geeksforgeeks . org/如何用 python 计算指数移动平均线/](https://www.geeksforgeeks.org/how-to-calculate-an-exponential-moving-average-in-python/)

**移动平均线**是用来分析长期股票价值的财务指标。即计算该长周期的平均值。**指数移动平均线**是一种**类型的移动平均线。**帮助用户过滤噪音，产生平滑曲线。在移动平均线 2 中非常受欢迎。

1.  Simple moving average
2.  Exponential moving average

简单移动平均只是通过对给定数据执行平均运算来计算平均值，但它会随着时间间隔而变化。但是在指数移动平均中，也使用简单平均计算其平均值，但是由于最新值具有更大的权重，因此给新增加的值赋予了更大的权重。

**公式**

> 均线<sub>今日</sub> =(值<sub>今日</sub> *(不变/(1+天数))+(均线<sub>昨日</sub> *(1-(不变/(1+天数)) )

今天的指数移动平均值是使用指数移动平均值的前一个值计算的。这里，旧值的权重较小，而新值的权重较大。数值权重的减少是使用称为**衰减的**常数**值计算的。**所以随着天数的增加，数值变得不太显著。它有助于防止价值的波动。

## ewm 方法在大熊猫中的应用

指数加权平均法用于计算以衰减常数为参数的均线。

**语法**

> data frame name . ewm(com = value)

**例 1:**

与原始股票值相比，均线值的曲线很不平滑，这表明指数移动平均线的性质。

## 蟒 3

```
# import necessary packages
import pandas as pd
import matplotlib.pyplot as plt

# create a dataframe
stockValues = pd.DataFrame(
    {'Stock_Values': [60, 102, 103, 104, 101,
                      105, 102, 103, 103, 102]})

# finding EMA
# use any constant value that results in
# good smoothened curve
ema = stockValues.ewm(com=0.4).mean()

# Comparison plot b/w stock values & EMA
plt.plot(stockValues, label="Stock Values")
plt.plot(ema, label="EMA Values")
plt.xlabel("Days")
plt.ylabel("Price")
plt.legend()
plt.show()
```