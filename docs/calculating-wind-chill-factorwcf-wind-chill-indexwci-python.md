# 计算 Python 中的风寒因子(WCF)或风寒指数(WCI)

> 原文:[https://www . geesforgeks . org/computing-wind-chill-factory wcf-wind-chill-index wci-python/](https://www.geeksforgeeks.org/calculating-wind-chill-factorwcf-wind-chill-indexwci-python/)

**W** ind-chill 或 **W** indchill 是由于空气的流动，身体在暴露的皮肤上感觉到的空气温度的降低。风寒的作用是增加热量散失的速度，更快地将较热的物体降低到环境温度。

以下是加拿大、英国和美国在 2001 年采用的计算和分析风寒指数的标准公式:

> t<sub>WC</sub>(WCI)= 13.12+0.6215t<sub>a</sub>–11.37v<sup>+0.16</sup>+0.3965t<sub>a</sub>v<sup>+0.16</sup>
> 在哪里
> 
> T <sub>wc</sub> =风寒指数(基于摄氏度温标)
> T <sub>a</sub> =气温(摄氏度)
> v =风速(英里每小时)

示例:

```
Input: 
Air Temperature = 28
Wind Speed = 80
Output: 30
Calculation done using the above formula:
WCI = 13.12 + 0.6215 * (28) - 
      11.37 * (80)**0.16 + 
      0.3965 * 28 * 80**0.16

```

```
Input: 
Air Temperature = 42
Wind Speed = 150
Output: 51
Calculation done using the above formula:
WCI = 13.12 + 0.6215 * (42) - 
      11.37 * (150)**0.16 + 
      0.3965 * 42 * 150**0.16

```

```
# Python program to calculate WCI
import math

# funtion to calculate WCI
def WC(temp, wi_sp):

    # Calculating Wind Chill Index (Twc)
    wci = 13.12+0.6215*temp- 11.37*math.pow(wi_sp, 0.16) + \
          0.3965*temp*math.pow(wi_sp, 0.16)
    return wci

# Taking the Air Temperature (Ta) 
temp = 42

# Taking the Wind Speed (v) 
wi_sp = 150

print("The Wind Chill Index is", int(round(WC(temp, wi_sp))))
```

输出:

```
The Wind Chill Index is 51

```

本文由 [**【钦莫伊蕾恩卡】**](https://auth.geeksforgeeks.org/profile.php?user=lenkachinmoy) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用[contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org)写一篇文章或者把你的文章邮寄到 contribute@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。