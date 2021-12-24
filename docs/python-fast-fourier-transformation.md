# Python |快速傅里叶变换

> 原文:[https://www . geesforgeks . org/python-快速傅立叶变换/](https://www.geeksforgeeks.org/python-fast-fourier-transformation/)

这是一种在序列的离散傅里叶变换计算中起着非常重要作用的算法。它将空间或时间信号转换成频域信号。
离散傅立叶变换信号是通过将值序列分布到不同的频率分量而产生的。直接在傅里叶变换上进行转换在计算上过于昂贵。因此，使用快速傅立叶变换，因为它通过将离散傅立叶变换矩阵分解为稀疏因子的乘积来快速计算。因此，它将离散傅立叶变换的计算复杂度从 0(N<sup>2</sup>)降低到 0(N log N)。在处理大型数据集时，这是一个巨大的差异。此外，在存在舍入误差的情况下，与直接的离散傅立叶变换定义相比，快速傅立叶变换算法非常精确。

这种变换是从配置空间到频率空间的转换，这对于探索某些问题的变换以便更有效地计算以及探索信号的功率谱都是非常重要的。这个翻译可以是从 x <sub>n</sub> 到 X <sub>k</sub> 。它将空间或时间数据转换为频域数据。

![](img/1f33bf7a2bc51d447135f1fbdd8ef8d4.png)

## **sympy . discrete . transforms . FFT():**

它可以在复域中进行离散傅里叶变换。
由于**基数-2 快速傅立叶变换**要求样本点数为 2 的幂，因此序列会自动向右填充零。对于短序列，仅将此方法与默认参数一起使用，因为序列的大小会增加表达式的复杂性。

```

Parameters : 
-> seq : [iterable] sequence on which DFT is to be applied.
-> dps : [Integer] number of decimal digits for precision.

Returns : 
Fast Fourier Transform

```

**例 1 :**

```
# import sympy 
from sympy import fft

# sequence 
seq = [15, 21, 13, 44]

# fft
transform = fft(seq)
print (transform)
```

**输出:**

```
FFT : [93, 2 - 23*I, -37, 2 + 23*I]
```

 **例 2 :**

```
# import sympy 
from sympy import fft

# sequence 
seq = [15, 21, 13, 44]

decimal_point = 4

# fft
transform = fft(seq, decimal_point )
print ("FFT : ", transform)
```

**输出:**

```
FFT :  [93, 2.0 - 23.0*I, -37, 2.0 + 23.0*I]

```