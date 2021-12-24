# Python 中的数字带通巴特沃斯滤波器

> 原文:[https://www . geeksforgeeks . org/digital-band-pass-butterworth-filter-in-python/](https://www.geeksforgeeks.org/digital-band-pass-butterworth-filter-in-python/)

在本文中，我们将讨论如何使用 Python 设计数字低通巴特沃斯滤波器。巴特沃斯滤波器是一种信号处理滤波器，设计为在通带内具有尽可能平坦的频率响应。让我们采用以下规格来设计滤波器，并观察数字巴特沃兹滤波器的幅度、相位和脉冲响应。

## **什么是数字带通滤波器？**

带通滤波器是一种通过一个范围内的频率并拒绝该范围外的频率的滤波器。

## **与高通&低通:**有何不同

主要区别可以通过观察带通滤波器的幅度响应发现。滤波器的通带具有特定的范围，这意味着该范围内的唯一信号可以通过带通滤波器。任何不在指定范围内的信号都会被滤波器拒绝。

**规格如下:**

*   Sampling rate 40 kHz
*   The passband edge frequency is 1400 Hz-2100 Hz.
*   The stop band edge frequency is 1050 Hz-2450 Hz.
*   Pass-band ripple 0.4 dB
*   The minimum stopband attenuation is 50 dB

我们将绘制滤波器的幅度、相位和脉冲响应。

**分步方法:**

在开始之前，首先，我们将创建一个用户定义的函数来转换边缘频率，我们将其定义为 *convert()* 方法**。**

## 蟒 3

```
# explicit function to convert
# edge frequencies
def convertX(f_sample, f):
    w = []

    for i in range(len(f)):
        b = 2*((f[i]/2)/(f_sample/2))
        w.append(b)

    omega_mine = []

    for i in range(len(w)):
        c = (2/Td)*np.tan(w[i]/2)
        omega_mine.append(c)

    return omega_mine
```

下面是步骤:

**步骤 1:** 导入所有必需的库。

## 蟒 3

```
# import required modules 
import numpy as np 
import matplotlib.pyplot as plt 
from scipy import signal 
import math
```