# Python 中的数字带阻巴特沃斯滤波器

> 原文:[https://www . geeksforgeeks . org/digital-band-reject-butterworth-filter-in-python/](https://www.geeksforgeeks.org/digital-band-reject-butterworth-filter-in-python/)

在本文中，我们将讨论如何使用 Python 设计数字带阻巴特沃斯滤波器。巴特沃斯滤波器是一种信号处理滤波器，设计为在通带内具有尽可能平坦的频率响应。让我们采用以下规格来设计滤波器，并观察数字巴特沃兹滤波器的幅度、相位和脉冲响应。

## **什么是数字带阻滤波器？**

带通滤波器是一种通过一个范围内的频率并拒绝该范围外的频率的滤波器。

## **它与高通、低通&带通有什么不同:**

主要区别可以通过观察带通滤波器的幅度响应发现。在带阻滤波器中，指定频率范围内的所有信号都会被滤波器抑制。

**规格如下:**

*   Sampling rate is 12 kHz.
*   The passband edge frequency is 2100 Hz-4500 Hz.
*   The stop band edge frequency is 2700 Hz-3900 Hz.
*   Pass-band ripple is 0.6 dB.
*   The minimum stopband attenuation is 45 dB.

我们将绘制滤波器的幅度、相位和脉冲响应。

### **逐步逼近**:

在开始之前，首先，我们将创建一个用户定义的函数来转换边缘频率，我们将其定义为 convert()方法。

## 蟒 3

```
# explicit function to convert
# edge frequencies

def convertX(f_sample, f):
    w = []

    for i in range(len(f)):
        b = 2*((f[i]/2) / (f_sample/2))
        w.append(b)

    omega_mine = []

    for i in range(len(w)):
        c = (2/Td)*np.tan(w[i]/2)
        omega_mine.append(c)

    return omega_mine
```

**步骤 1:** 导入所有必要的库。

## 蟒 3

```
# import required modules
import numpy as np
import matplotlib.pyplot as plt
from scipy import signal
import math
```

**步骤 2:** 用给定的过滤器规格定义变量。

## 蟒 3

```
# Specifications of Filter

# sampling frequency
f_sample = 12000

# pass band frequency
f_pass = [2100, 4500]

# stop band frequency
f_stop = [2700, 3900]

# pass band ripple
fs = 0.5

# Sampling Time
Td = 1

# pass band ripple
g_pass = 0.6

# stop band attenuation
g_stop = 45
```