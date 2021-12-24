# Python 中的数字高通巴特沃斯滤波器

> 原文:[https://www . geeksforgeeks . org/digital-高通-巴特沃斯-python 中的滤波器/](https://www.geeksforgeeks.org/digital-high-pass-butterworth-filter-in-python/)

在本文中，我们将讨论如何使用 Python 设计数字高通巴特沃斯滤波器。巴特沃斯滤波器是一种信号处理滤波器，设计为在通带内具有尽可能平坦的频率响应。让我们采用以下规格来设计滤波器，并观察数字巴特沃兹滤波器的幅度、相位和脉冲响应。

## **什么是高通滤波器？**

高通滤波器是一种电子滤波器，通过频率高于某一截止频率的信号，衰减频率低于截止频率的信号。每个频率的衰减取决于滤波器设计。

## **数字高通滤波器之间的差异&数字低通滤波器:**

最显著的区别是滤波器的幅度响应，我们可以清楚地观察到，在**高通滤波器**的情况下，滤波器通过频率高于某一截止频率的信号，衰减频率低于截止频率的信号，而在**低通滤波器**的情况下，滤波器通过频率低于某一截止频率的信号，衰减频率高于规定截止值的所有信号。

**规格如下:**

*   采样速率为 3.5 千赫
*   1050 赫兹的通带边缘频率
*   600 赫兹的阻带边缘频率
*   1 分贝的通带纹波
*   最小阻带衰减 50 分贝

我们将绘制滤波器的幅度、相位和脉冲响应。

**分步方法:**

**步骤 1:** 导入所有必需的库。

## 蟒蛇 3

```py
# Import required modules
import numpy as np
import matplotlib.pyplot as plt
from scipy import signal
import math
```

**步骤 2:** 用给定的过滤器规格定义变量。

## 蟒蛇 3

```py
# Specifications of Filter

 # sampling frequency
f_sample = 3500

# pass band frequency
f_pass = 1050

# stop band frequency
f_stop = 600

# pass band ripple
fs = 0.5

# pass band freq in radian
wp = f_pass/(f_sample/2)  

# stop band freq in radian
ws = f_stop/(f_sample/2) 

# Sampling Time
Td = 1 

 # pass band ripple
g_pass = 1

# stop band attenuation
g_stop = 50
```

**步骤 3:** 使用*signal . butford()*方法构建滤波器。

## 蟒蛇 3

```py
# Conversion to prewrapped analog frequency
omega_p = (2/Td)*np.tan(wp/2)
omega_s = (2/Td)*np.tan(ws/2)

# Design of Filter using signal.buttord function
N, Wn = signal.buttord(omega_p, omega_s, g_pass, g_stop, analog=True)

# Printing the values of order & cut-off frequency!
print("Order of the Filter=", N)  # N is the order
# Wn is the cut-off freq of the filter
print("Cut-off frequency= {:.3f} rad/s ".format(Wn))

# Conversion in Z-domain

# b is the numerator of the filter & a is the denominator
b, a = signal.butter(N, Wn, 'high', True)
z, p = signal.bilinear(b, a, fs)
# w is the freq in z-domain & h is the magnitude in z-domain
w, h = signal.freqz(z, p, 512)
```

**输出:**

![](img/e347aadcea9a0fc577beeccffb2ed780.png)

**第 4 步:**绘制震级响应。

## 蟒蛇 3

```py
# Magnitude Response
plt.semilogx(w, 20*np.log10(abs(h)))
plt.xscale('log')

plt.title('Butterworth filter frequency response')
plt.xlabel('Frequency [Hz]')
plt.ylabel('Amplitude [dB]')
plt.margins(0, 0.1)

plt.grid(which='both', axis='both')
plt.axvline(100, color='green')
plt.show()
```

**输出:**

![](img/63053d39638b4432e2e3b8ffeb04c4ed.png)

**步骤 5:** 绘制脉冲响应。

## 蟒蛇 3

```py
# Impulse response
imp = signal.unit_impulse(40)
c, d = signal.butter(N, 0.5)
response = signal.lfilter(c, d, imp)

# Illustrating impulse response
plt.stem(np.arange(0, 40), imp, markerfmt='D', use_line_collection=True)
plt.stem(np.arange(0, 40), response, use_line_collection=True)
plt.margins(0, 0.1)

plt.xlabel('Time [samples]')
plt.ylabel('Amplitude')
plt.grid(True)
plt.show()
```